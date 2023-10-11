### Get token from cloud side (on Master Node)
```
sudo keadm gettoken
```{{execute}}

# On Edge 
<br>
<br>
Next, run keadm join to join edge node.

```
sudo keadm join --cloudcore-ipport="Cloudcore-IP:10000" --token={token} --kubeedge-version=v1.14.2 --runtimetype=remote --remote-runtime-endpoint=unix:///var/run/cri-dockerd.sock

```{{execute}}

keadm join will install edgecore and mqtt, and --cloudcore-ipport flag is a mandatory flag.   

**Now you can see KubeEdge edgecore is running.**