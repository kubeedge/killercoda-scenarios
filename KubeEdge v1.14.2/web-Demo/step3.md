### Build PI Player App

Cross-complie the PI Player App which will run on the RaspBerry PI and play the expected track.

```
 cd $GOPATH/src/github.com/kubeedge/examples/web-demo/pi-player-app/

```
```
 export GOARCH=arm
 export GOOS="linux"
 export GOARM=6
 export CGO_ENABLED=1
 export CC=arm-linux-gnueabi-gcc
```
```
 go build -o pi-player-app main.go
```