# 安装kind   
<br> 
 kind 即 Kubernetes In Docker，将 k8s 所需要的所有组件全部部署在一个docker容器中，是一套开箱即用的 k8s 环境搭建方案，可以让我们快速的搭建k8s测试平台。

执行以下命令安装kind:
```
curl -Lo ./kind https://github.com/kubernetes-sigs/kind/releases/download/v0.11.1/kind-linux-amd64  
chmod +x ./kind  
mv ./kind /usr/local/bin/kind
```{{execute}}  
    
<br>
<br>

为了后续用命令行管理集群，我们需要安装Kubectl：    
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.22.6/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
```{{execute}}

