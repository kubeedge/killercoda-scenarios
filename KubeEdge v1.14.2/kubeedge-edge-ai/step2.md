1. Calling the camera defaults to a local camera, and you can change the IP address of the camera by using `-- camera = ip:port`  
2. You can add the `--show` parameter to determine whether the recognition results are displayed on the display.  
3. When adding the `--show` parameter, you can pass in face data via the S key on the keyboard  
4. Copy the model to the local `/model/facenet` directory before running it

#### Moving object detection  
``` 
cd motion detection  
docker build -t motion-detection:dev 
```
```
cd ..
kubectl apply -f motionDetectionDeployment.yaml
```
