# Deploy cloudcore (on Master Node)

keadm init will install cloudcore, generate the certs and install the CRDs.
--advertise-address (non-mandatory flag) is the address exposed by the cloud side (will be added to the SANs of the CloudCore certificate), the default value is the local IP.

```
sudo keadm deprecated init --advertise-address="CloudCore-IP" --kubeedge-version=1.14.2 --kube-config=/root/.kube/config

```{{execute}} 

## check if cloudcore running successfully:

```
ps -elf | grep cloudcore

```{{execute}}

**Now you can see KubeEdge cloudcore is running.**