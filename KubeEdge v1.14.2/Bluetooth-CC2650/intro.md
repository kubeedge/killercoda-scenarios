# Bluetooth With KubeEdge Using CC2650


Users can make use of KubeEdge platform to connect and control their bluetooth devices, provided, the user is aware of the of the data sheet information for their device.
Kubernetes Custom Resource Definition (CRD) and KubeEdge bluetooth mapper is being used to support this feature, using which users can control their device from the cloud. Texas Instruments [CC2650 SensorTag device](http://processors.wiki.ti.com/index.php/CC2650_SensorTag_User%27s_Guide) is being shown here as an example.


## Description

KubeEdge support for bluetooth protocol has been demonstrated here by making use of Texas Instruments CC2650 SensorTag device.
This section contains instructions on how to make use of bluetooth mapper of KubeEdge to control CC2650 SensorTag device.

  We will only be focusing on the following features of CC2650 :-

  ```shell
  1. IR Temperature
  2. IO-Control :
      2.1 Red Light
      2.2 Greem Light
      2.3 Buzzer
      2.4 Red Light with Buzzer
      2.5 Green Light with Buzzer
      2.6 Red Light along with Green Light
      2.7 Red Light, Green Light along with Buzzer

  ```

  The bluetooth mapper has the following major components :-
   - Action Manager
   - Scheduler
   - Watcher
   - Controller
   - Data Converter

  More details on bluetooth mapper can be found [here](https://github.com/kubeedge/kubeedge/blob/master/docs/mappers/bluetooth_mapper.md#bluetooth-mapper).


## Prerequisites

### Hardware Prerequisites

1. Texas instruments CC2650 bluetooth device
2. Linux based edge node with bluetooth support  (An Ubuntu 18.04 laptop has been used in this demo)

### Software Prerequisites

1. Golang (1.14+)
2. KubeEdge (v1.5+)