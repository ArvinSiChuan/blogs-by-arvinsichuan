# CRI-Installation
## Docker
```bash
# ADD GPG KEY 
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
# Add Repo
sudo add-apt-repository \
  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) \
  stable"
  
## Alternative mirrors
sudo add-apt-repository \
  "deb [arch=amd64]  https://mirrors.tuna.tsinghua.edu.cn/docker-ce/linux/ubuntu \
  $(lsb_release -cs) \
  stable"

# Reload the repo and install docker-ce
sudo apt-get update
sudo  apt-get install -y   containerd.io=1.2.13-2   docker-ce=5:19.03.11~3-0~ubuntu-$(lsb_release -cs)   docker-ce-cli=5:19.03.11~3-0~ubuntu-$(lsb_release -cs)

# modify docker-daemon json file
vim /etc/docker/daemon.json

```
Ref for `daemon.json`:
```json
{
  "registry-mirrors": [
    "https://urrxb38a.mirror.aliyuncs.com/"
  ],
  "live-restore": true,
  "exec-opts": ["native.cgroupdriver=systemd"],
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "100m"
  },
  "storage-driver": "overlay2"
}
```
### Common Troubleshoot for docker

#### `Your kernel does not support cgroup swap limit capabilities` OR `WARNING: No swap limit support` -> No Swap Support in the kernel cgroup, possibly not enabled. To enable, do:  
```bash
# SET/ADD GRUB_CMDLINE_LINUX="cgroup_enable=memory swapaccount=1" in /etc/default/grub
# sudo update-grub && sudo reboot
```

