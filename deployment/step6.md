# Build and Run Cloud 

This step builds and runs the cloud component

Change path to $GOPATH/src/github.com/kubeedge/kubeedge.

`cd $GOPATH/src/github.com/kubeedge/kubeedge/cloud`{{execute HOST1}}

`make`{{execute HOST1}}

Wait untill build is completed.

Run cloud.

`./edgecontroller`{{execute HOST1}}
