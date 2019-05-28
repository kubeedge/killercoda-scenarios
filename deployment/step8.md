# Check Status

This step helps to check the status of created edge nodes.

Open a new terminal by clicking on + near to master node.

Set GOPATH for this terminal.

`export GOPATH=/root/kubeedge`{{execute}}
 
Use below command to check the edge node status.

`kubectl get nodes`{{execute}}

The status would be master(Ready) and edge nodes(Not Ready/Unknown)
 