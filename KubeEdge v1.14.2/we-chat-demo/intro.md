## Prerequisites

### Hardware Prerequisites

* RaspBerry PI (RaspBerry PI 3 has been used for this demo).
  The RaspBerry PI is also the edge node to which the speaker will be connected.

* A speaker for playing the music.

### Software Prerequisites

* A running Kubernetes cluster.

* KubeEdge 0.3.0+

  *Note*:

  when you setup edgecore on the RaspBerry PI,
  Please set the `mqtt mode` as `2` and replace `0.0.0.0` with your Kubernetes master ip address.

* In order to control the speaker and play the expected track, we need to manage the speaker connected to the RaspBerry PI.
  KubeEdge allows us to manage devices using Kubernetes custom resource definitions.
  The design proposal is [here](https://github.com/kubeedge/kubeedge/blob/master/docs/proposals/device-crd.md).
  Apply the CRD schema yamls available [here](https://github.com/kubeedge/kubeedge/tree/master/build/crds/devices) using kubectl.