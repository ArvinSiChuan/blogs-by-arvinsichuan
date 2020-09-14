# Cluster Upgrade
[← Back](../way-to-cka)

## Check the Possible Upgrade Plan  
```bash
kubeadm upgrade plan
```

## Upgrade the control flight nodes(s)(master node[s])  
1. Upgrade Kube-system Component
```bash
kubeadmin upgrade apply v1.19.1 # for example, to upgrade v1.19.0 to v1.19.1
```
2. Upgrade `kubeadmin`,`kubelet`,`kubeclt` with package manager or build release binaries

## Upgrade the working nodes
1. Upgrade Kube-system Component
```bash
kubeadmin upgrade apply v1.19.1 # for example, to upgrade v1.19.0 to v1.19.1
```
2. Upgrade `kubeadmin`,`kubelet`,`kubeclt` with package manager or build release binaries

## References  
- [kubeadm-upgrade](https://kubernetes.io/docs/reference/setup-tools/kubeadm/kubeadm-upgrade/)
