#### Copy the configuration file that has been provided, into its correct path. Please note that the configuration file can be altered as to suit your requirement

```
cp $GOPATH/src/github.com/kubeedge/examples/bluetooth-CC2650-demo/config.yaml

$GOPATH/src/github.com/kubeedge/kubeedge/mappers/bluetooth_mapper/configuration/
```

#### Build the mapper by following the steps given below.

```
cd $GOPATH/src/github.com/kubeedge/kubeedge
make bluetoothdevice_image
docker tag bluetooth_mapper:v1.0 <your_dockerhub_username>/bluetooth_mapper:v1.0
docker push <your_dockerhub_username>/bluetooth_mapper:v1.0
```

<br>
Note: Before trying to push the docker image to the remote repository please ensure that you have signed into docker from your node, if not please type the followig command to sign in
docker login
<br>
Please enter your username and password when prompted


