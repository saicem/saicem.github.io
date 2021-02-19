生成ssh公钥
`
ssh-keygen -t rsa
`
将生产的 id_rsa.pub 的内容复制至linux上的 ~/.ssh/authorized_keys 即可实现免密登录