# Generate Certificates

This step generates the certificates necessary for kubeedge setup.

RootCA certificate and a cert/key pair is required to have a setup for KubeEdge. 

Same cert/key pair can be used in both cloud and edge.

The below command will generate the certificates.

`$GOPATH/src/github.com/kubeedge/kubeedge/build/tools/certgen.sh genCertAndKey edge`{{execute}}

The cert/key will be generated in the /etc/kubeedge/ca and /etc/kubeedge/certs respectively.

_It is acceptable to keep certificate in any desired path but ensure to update the corresponding path in 
$GOPATH/src/github.com/kubeedge/kubeedge/cloud/conf/controller.yaml._
