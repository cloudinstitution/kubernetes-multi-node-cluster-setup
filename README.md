# kubernetes-multi-node-cluster-setup

## Make sure to enable 6443 port in the security group

<img width="1209" height="468" alt="image" src="https://github.com/user-attachments/assets/7fc5e558-ddf7-4c45-8e82-841cbde96663" />

## Initialize a Kubernetes cluster using the kubeadm

$ kubeadm init --pod-network-cidr=10.244.0.0/16

## install CNI 

$ kubectl apply -f https://raw.githubusercontent.com/flannel-io/flannel/master/Documentation/kube-flannel.yml


## To start using your cluster, you need to run the following as a regular user

$ mkdir -p $HOME/.kube 
$ sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
$ sudo chown $(id -u):$(id -g) $HOME/.kube/config
