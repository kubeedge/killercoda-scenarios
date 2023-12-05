# Deployment of example setup
## Prerequisites
* Bash version 4.4.19+
* Go compiler version 1.11.4+
* Go dep and glide package managers
* sshpass
* Kubernetes cluster

## How to configure
### Script Configurations

Environment variable configurations : &lt;SPIRE\_PATH&gt;/edge.env

```
    export CLOUD_VM_USER=vm1
    export CLOUD_VM_PASS=<cloud vm password used for ssh>
    export CLOUD_VM_IP=192.168.56.101
    export SPIRE_PATH=/opt/spire
    export NODE_ID=fakenodeid
    export PROJECT_ID=dummyprojectid
    export MQTT_EXT_PORT=2883
    export MQTT_INT_PORT=2884
    export EDGE_HUB_IP=127.0.0.1
    export EDGE_HUB_PORT=20000
    export EDGE_VM_IP=192.168.56.102
```

Environment variable configurations : &lt;SPIRE\_PATH&gt;/cloud.env
```
    export CLOUD_HUB_IP=127.0.0.1
    export CLOUD_HUB_PORT=20000
    export KUBECONFIG="/home/vm1/.kube/config"
    export CLOUD_VM_IP=192.168.56.101
```
## How to setup and use

1\. Copy the release files to cloud node and edge node at path /opt/spire/.

2\. Update the IP , port and spire path in the above listed configurations.

3\. Create an edge node.

4\. In cloud node , execute deploy-cloud.sh.

5\. In edge node , execute deploy-edge.sh. Edged reports ready status to edgecontroller. To verify node status, in cloud vm, execute

```
kubectl get nodes
```