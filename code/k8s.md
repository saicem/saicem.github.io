# Kubernetes

## k3s 初始化安装及配置

```bash
# 解决 failed to get sandbox image "rancher/mirrored-pause:3.6"
sudo mkdir -p /etc/rancher/k3s
cat << EOF > /etc/rancher/k3s/registries.yaml
mirrors:
  "docker.io":
    endpoint:
      - "https://mirror.ccs.tencentyun.com" 
EOF

# 卸载已安装的 k3s
/usr/local/bin/k3s-uninstall.sh
# 镜像源安装 k3s
curl -sfL https://rancher-mirror.rancher.cn/k3s/k3s-install.sh | INSTALL_K3S_MIRROR=cn sh -
# 将配置复制到本用户以正常使用 kubectl
sudo cat /etc/rancher/k3s/k3s.yaml > ~/.kube/config
```

## 配置 traefik 自动更新证书

### 持久化 acme.json

创建 PersistentVolume 和 PersistentVolumeClaim

```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: traefik-acme-pv
spec:
  capacity:
    storage: 10Mi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: "/data/traefik/acme"
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: traefik-acme-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 10Mi
```

```bash
kubectl apply -f traefik-volume.yml -n kube-system
```

### 通过文件

准备 values.yaml

```yaml
additionalArguments:
  - --certificatesresolvers.default.acme.email=example@example.com
  - --certificatesresolvers.default.acme.storage=/data/acme.json
  - --certificatesresolvers.default.acme.httpchallenge.entrypoint=web

additionalVolumeMounts:
  - name: traefik-certs
    mountPath: /data

additionalVolumes:
  - name: traefik-certs
    persistentVolumeClaim:
      claimName: traefik-acme-pvc
```

更新 traefik 配置

```bash
helm upgrade traefik traefik/traefik -f traefik-values.yaml -n kube-system
```

### 通过命令行

```bash
export email=example@example.com

helm upgrade traefik traefik/traefik \
--set "additionalArguments[0]=--certificatesresolvers.default.acme.email=${email}" \
--set "additionalArguments[1]=--certificatesresolvers.default.acme.storage=/data/acme.json" \
--set "additionalArguments[2]=--certificatesresolvers.default.acme.httpchallenge.entrypoint=web" \
--set "additionalVolumes[0].name=traefik-certs" \
--set "additionalVolumes[0].persistentVolumeClaim.claimName=traefik-acme-pvc" \
--set "additionalVolumeMounts[0].name=traefik-certs" \
--set "additionalVolumeMounts[0].mountPath=/data" \
-n kube-system
```

### 查看 traefik 日志

```bash
kubectl logs -n kube-system -l app.kubernetes.io/name=traefik --tail=100 -f
```

### 更新对应 ingress 的 yaml

```yaml
metadata:
  annotations:
    kubernets.io/ingress.class: traefik
    traefik.ingress.kubernetes.io/router.entrypoints: websecure
    traefik.ingress.kubernetes.io/router.tls: "true"
    traefik.ingress.kubernetes.io/router.tls.certresolver: default
```
