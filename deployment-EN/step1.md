# Install kind   
<br> 
Kind is a tool for running local Kubernetes clusters using Docker container “nodes”.

Run the command below to intsall kind:
```
curl -Lo ./kind https://github.com/kubernetes-sigs/kind/releases/download/v0.11.1/kind-linux-amd64  
chmod +x ./kind  
mv ./kind /usr/local/bin/kind
```{{execute}}  
    
<br>
<br>

In order to manage the cluster later using the CLI, install Kubectl：    
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.22.6/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
```{{execute}}


