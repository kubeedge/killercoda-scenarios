### Build the mapper to run in RaspBerry-Pi.

```
cd $GOPATH/src/github.com/kubeedge/examples/temperature-demo
```
```
docker build -t <your_dockerhub_username>/kubeedge-temperature-mapper:<your_tag> .
docker push <your_dockerhub_username>/kubeedge-temperature-mapper:<your_tag>
```

##### Note: Before trying to push the docker image to the remote repository please ensure that you have signed into docker from your node, if not please type the followig command to sign in