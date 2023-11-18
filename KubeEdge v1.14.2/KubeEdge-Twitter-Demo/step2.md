### Create the device model and device instance for the speaker

With the Device CRD APIs now installed in the cluster , we now create the device model and instance for the speaker using the yaml files under examples/crds.

### Create Secret for Twitter Credentials
- The cloud app in the demo needs to watch KubeEdge tweets. For this the application needs to sign the requests with a Twitter account.
Follow the steps mentioned here [Guide for reference](https://docs.inboundnow.com/guide/create-twitter-application/) to generate the OAuth credentials. Create a Kubernetes Secret`twittersecret` with the credentials as below :

```
kubectl create secret generic twittersecret --from-literal=CONSUMER_KEY=<your_consumer_key> --from-literal=CONSUMER_SECRET=<your_consumer_secret> --from-literal=ACCESS_TOKEN=<your_access_token> --from-literal=ACCESS_TOKEN_SECRET=<your_access_token_secret>
```