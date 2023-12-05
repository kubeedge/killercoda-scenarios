1. Make sure cc2531 USB Sniffer is connected to your device and there is a directory `/dev/ttyacm0`

#### mapper

``` 
cd mapper
docker build -t mapper:v1 .
kubectl apply -f deployMapper.yaml  
```  
During face recognition, the ZigBee switch will be turned on if the recognition result exists in the face database. If the result is unknown, the Zigbee switch will be turned off. The status information of the switch can be viewed through the Device Switch in the cloud.