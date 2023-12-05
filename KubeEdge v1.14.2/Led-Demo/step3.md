6. Build the mapper to run in RaspBerry-Pi.

```
cd $GOPATH/src/github.com/kubeedge/examples/led-raspberrypi/
make 
```
or ***make led_light_mapper***

```
docker tag led-light-mapper:v1.1 <your_dockerhub_username>/led-light-mapper:v1.1
docker push <your_dockerhub_username>/led-light-mapper:v1.1
```

Note: Before trying to push the docker image to the remote repository please ensure that you have signed into docker from your node, if not please type the followig command to sign in <br>

docker login<br>

Please enter your username and password when prompted