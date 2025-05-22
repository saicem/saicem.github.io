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

# 查看 traefik 日志
kubectl logs -n kube-system -l app.kubernetes.io/name=traefik --tail=100 -f

# 更新 traefik 配置
helm upgrade traefik traefik/traefik -f traefik-values.yaml -n kube-system

```
