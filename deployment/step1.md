# Environment Setup for Cloud Node

This step basically sets up the environment required for deploying kubeedge.

Do kubeadm init

`kubeadm init --kubernetes-version $(kubeadm version -o short) --pod-network-cidr=10.244.0.0/16`{{execute HOST1}}

Perform following steps to start using the cluster:

`mkdir -p $HOME/.kube`{{execute HOST1}}

`sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config`{{execute HOST1}}

`sudo chown $(id -u):$(id -g) $HOME/.kube/config`{{execute HOST1}}

`kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/a70459be0084506e4ec919aa1c114638878db11b/Documentation/kube-flannel.yml`{{execute HOST1}}
 
Make k8s apiserver listen on insecure port 8080 and update insecure bind address to 
0.0.0.0 for edgecontroller/kubectl to work with http connection to Kubernetes apiserver. 
Update this parameters in the kube-apiserver.yaml file.

Edit - --insecure-port=8080

Add - --insecure-bind-address=0.0.0.0

The below command will open the file and update the details in the file as specified.

`vim /etc/kubernetes/manifests/kube-apiserver.yaml`{{execute HOST1}}

Create folder structre for cloning the base code.

`mkdir -p kubeedge/src`{{execute HOST1}}

Set GOPATH

`export GOPATH=/root/kubeedge`{{execute HOST1}}

Verify whether GOPATH is set correctly

`echo $GOPATH`{{execute HOST1}}
