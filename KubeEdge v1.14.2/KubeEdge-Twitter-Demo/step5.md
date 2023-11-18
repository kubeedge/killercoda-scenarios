### Build the track player app
- Cross-complie the PiApp which will run on the RPi and play the desired track.

#Pls give the appropriate arm version of your device

```
~/go/src/github.com/ke-twitter-demo$export GOARCH=arm
~/go/src/github.com/ke-twitter-demo$export GOOS="linux"
~/go/src/github.com/ke-twitter-demo$export GOARM=6                             
~/go/src/github.com/ke-twitter-demo$export CGO_ENABLED=1
~/go/src/github.com/ke-twitter-demo$export CC=arm-linux-gnueabi-gcc
~/go/src/github.com/ke-twitter-demo$ go build Pi_app/trackplayer.go
```