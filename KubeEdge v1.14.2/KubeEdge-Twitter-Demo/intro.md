## Prerequisites

### Hardware Prerequisites
- RaspBerry-Pi (RaspBerry-Pi 3 has been used for this demo). This will be the edge node to which the speaker will be connected.
- A speaker for playing the track.

### Software Prerequisites
- A running Kubernetes cluster.
- KubeEdge v1.5.0+
- In order to control the speaker and play the desired track , we need to manage the speaker connected to the rpi.
  KubeEdge allows us to manage devices using K8S custom resource definitions. The design proposal is [here](https://github.com/kubeedge/kubeedge/blob/master/docs/proposals/device-crd.md). Apply the CRD schema yamls available [here](https://github.com/kubeedge/kubeedge/tree/master/build/crds/devices) using kubectl.