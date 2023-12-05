#### zigbee2mqtt  

``` 
cd zigbee2mqtt
docker build -t zigbee2mqtt:v1 .
```

```
cd ..
kubectl apply -f deployzigbee2mqtt.yaml
```