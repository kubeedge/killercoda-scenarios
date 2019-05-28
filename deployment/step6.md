# Build and Run Cloud 

This step builds and runs the cloud component

Change path to $GOPATH/src/github.com/kubeedge/kubeedge.

`cd $GOPATH/src/github.com/kubeedge/kubeedge/cloud/conf`{{execute HOST1}}

Remove module devicecontroller in modules.yaml to avoid unnecessary error logs.

`vim modules.yaml`{{execute HOST1}}

`cd ..`{{execute HOST1}}

Build the cloud component.

`make`{{execute HOST1}}

Wait untill build is completed.

Run cloud.

`./edgecontroller`{{execute HOST1}}

Open a new terminal by clicking on + near to master node.