# Copy the certificate generated to edge node

Copy the certificates generated in master to the node01 in path /etc/kubeedge/ca and /etc/kubeedge/certs

`cd /etc`{{execute HOST2}}

Create path for copying certificates.

`mkdir kubeedge`{{execute HOST2}}

`cd kubeedge`{{execute HOST2}}

`mkdir ca`{{execute HOST2}}

`mkdir certs`{{execute HOST2}}

Copy the generated certificates.

`scp -r /etc/kubeedge/ca root@node01:/etc/kubeedge`{{execute HOST1}}

When prompted, give yes in master node.

`scp -r /etc/kubeedge/certs root@node01:/etc/kubeedge`{{execute HOST1}}

 _This is the default path. The certificates can be kept in any desired path but enusure that path is specified correctly for certificates in upcoming steps._
 