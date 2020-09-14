# K8s setup 

## Kubectl
**Mirror Configuration(Aliyun)**
```bash
# Gain root priviledges
curl https://mirrors.aliyun.com/kubernetes/apt/doc/apt-key.gpg | apt-key add - 
echo 'deb https://mirrors.aliyun.com/kubernetes/apt/ kubernetes-xenial main' >> /etc/apt/apt.conf.d/kubernetes-aliyun.list
 apt-get update
```