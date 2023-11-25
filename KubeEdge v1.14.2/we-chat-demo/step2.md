### Create Secret for WeChat Credentials

The KubeEdge WeChat App in the demo needs to serve behind WeChat.
For this the application needs to sign the requests with a WeChat Account.
Create a Kubernetes Secret `wechatsecret` with the credentials as below:

```
kubectl create secret generic wechatsecret \
--from-literal=AppID=<Your_WeChat_AppID> \
--from-literal=AppSecret=<Your_WeChat_AppSecret> \
--from-literal=Token=<Your_WeChat_Token> \
--from-literal=EncodingAESKey=<Your_WeChat_EncodingAESKey>
```