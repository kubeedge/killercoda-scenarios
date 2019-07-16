# Deploy Edge Node

Modify the $GOPATH/src/github.com/kubeedge/kubeedge/build/node.json file. 
Change metadata.name to name of the edge node to deploy.

`vim $GOPATH/src/github.com/kubeedge/kubeedge/build/node.json`{{execute HOST2 }}

Deploy node using the below command.

```sh
kubectl apply -f $GOPATH/src/github.com/kubeedge/kubeedge/build/node.json -s cloudhuburl:8080
```
_Replace cloudhuburl with the ip of the machine where cloud is running(use ens3 inet addr)._

Perform above two steps multiple times to create multiple nodes.

On successful creation of node, message "node/_edge node name given_ created" will be displayed. 

Pull docker image of edgecore(The image used for this tutorial is created from release-1.0).

`docker pull kubeedge/edgecore:v1.0.0`{{execute HOST2}}

Tag the image to kubeedge/edgecore:latest.

`docker tag kubeedge/edgecore:v1.0.0 kubeedge/edgecore:latest`{{execute HOST2}}
