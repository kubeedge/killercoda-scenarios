### Run the ke-tweeeter app

- The ke-tweeter-app runs in a VM on the cloud and watches for KubeTweets. It can deployed using a Kubernetes deployment yaml 

```
 cd $GOPATH/github.com/ke-twitter-demo/ke-tweeter/deployments/
 kubectl create -f ke-tweeter.yaml
```