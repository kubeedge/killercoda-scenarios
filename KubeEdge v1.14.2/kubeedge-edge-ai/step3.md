1. The camera information configuration is the same as face recognition
2. When a moving object appears in front of the camera, the program will record the video and save the result to the local directory /data/video

### Device module

#### Device & DeviceModel
``` 
cd crds
kubectl apply -f devicemodel.yaml
kubectl apply -f device.yaml
 ```  

When the device is connected, you can view the results of the cloud device synchronization through the following command
``` 
kubectl get device switch -oyaml -w 
```    