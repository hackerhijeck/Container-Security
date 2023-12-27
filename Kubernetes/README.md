## Kubernetes Installation:
#### Installation Steps:
```
$ sudo apt update
$ sudo apt install -y apt-transport-https
$ sudo apt install docker.io
$ systemctl start docker
$ systemctl enable docker
$ sudo apt install curl
$ sudo apt install -y apt-transport-https ca-certificates curl gpg

## For this sources.list.d file:

$ curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
$ echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list

## OR

$ curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
$ cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
deb http://apt.kubernetes.io/ kubernetes-xenial main
EOF

## Next Steps:

$ sudo apt update
$ sudo apt install -y kubelet kubeadm kubectl kubernetes-cni
$ swapoff -a
$ nano /etc/fstab   (# Comment out swap line in fstab so that it remains disabled after reboot)
$ kubeadm init --kubernetes-version stable --token-ttl 0 --pod-network-cidr=192.168.0.0/16   (wait for 1/2 miniute)
$ mkdir -p $HOME/.kube
$ sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
$ sudo chown $(id -u):$(id -g) $HOME/.kube/config
$ kubectl taint nodes --all node-role.kubernetes.io/master-
$ kubectl apply -f https://docs.projectcalico.org/v2.6/getting-started/kubernetes/installation/hosted/kubeadm/1.6/calico.yaml
$ kubectl get po -n kube-system
$ kubectl get pods
$ kubectl get pods --all-namespaces
```
