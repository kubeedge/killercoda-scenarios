# Environment Setup for Edge Nodes

### Install GoLang and set GOROOT and GOPATH

Download Go Lang Package
`wget https://dl.google.com/go/go1.10.3.linux-amd64.tar.gz`{{execute HOST2}}

Untar the downloaded package
`sudo tar -xvf go1.10.3.linux-amd64.tar.gz`{{execute HOST2}}

Move go to the path /usr/local
`sudo mv go /usr/local`{{execute HOST2}}

Export GOROOT
`export GOROOT=/usr/local/go`{{execute HOST2}}

Create path for kubeedge
`mkdir -p kubeedge/src`{{execute HOST2}}

Export GOPATH
`export GOPATH=/root/kubeedge`{{execute HOST2}}

Update PATH 
`export PATH=$GOPATH/bin:$GOROOT/bin:$PATH`{{execute HOST2}}
