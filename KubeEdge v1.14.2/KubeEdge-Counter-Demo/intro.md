## Prerequisites

### Hardware Prerequisites

* RaspBerry PI (RaspBerry PI 4 has been used for this demo).

### Software Prerequisites

* A running Kubernetes cluster.

  *NOTE*:

  add follows `--insecure-port=8080` and `--insecure-bind-address=0.0.0.0` options into */etc/kubernetes/manifests/kube-apiserver.yaml*

* KubeEdge v1.5+

* MQTT Broker is running on Raspi.

## Steps to run the demo

### Create the device model and device instance for the counter

With the Device CRD APIs now installed in the cluster, we create the device model and instance for the counter using the yaml files.

