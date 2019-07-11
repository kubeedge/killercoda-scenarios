# Clone Base Code

This step clones the code from kubeedge repository. 

This clones code to the master node and keeps it in GOPATH.
`git clone https://github.com/kubeedge/kubeedge.git $GOPATH/src/github.com/kubeedge/kubeedge`{{execute HOST1}}

Check out to version 1.0

`cd $GOPATH/src/github.com/kubeedge/kubeedge`{{execute HOST1}}

`git checkout v1.0.0`{{execute HOST1}}

This clones code to node01 and keeps it in GOPATH.
`git clone https://github.com/kubeedge/kubeedge.git $GOPATH/src/github.com/kubeedge/kubeedge`{{execute HOST2}}

Check out to version 1.0

`cd $GOPATH/src/github.com/kubeedge/kubeedge`{{execute HOST2}}

`git checkout v1.0.0`{{execute HOST2}}
