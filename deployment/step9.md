# Run edge nodes inside containers

Go to the below mentioned path.

`cd $GOPATH/src/github.com/kubeedge/kubeedge/build/edge`{{execute HOST2}}

_./run_daemon.sh only_run_edge mqtt=0.0.0.0:1883 cloudhub=0.0.0.0:10000 edgename=node image="kubeedge/edgecore:latest" containername=container_
 
 Use the above command to deploy created edge node inside container.
 
 _Replace 0.0.0.0 in cloudhub with the ip of the machine where cloud is running._
 
_Replace node with name of node created._
 
_Replace container with name desired for container._
 
_Repeat this step to deploy multiple nodes._
 
Check Status
 
`kubectl get nodes`{{execute}}
 
The state of edge node will be Ready.
