# Setup Edge Side (KubeEdge Worker Node)
<br>
Run keadm gettoken will return the token, which will be used when joining edge nodes. Save the returned value to the variable token_value.

`token_value=$(keadm gettoken)`{{execute}}
<br>
<br>
Next, run keadm join to join edge node.  
  
`keadm join --cloudcore-ipport=172.30.1.2:10000 --token=${token_value}`{{execute}}  


keadm join will install edgecore and mqtt, and --cloudcore-ipport flag is a mandatory flag.   
<br> 
<br>
**Now you can see KubeEdge edgecore is running.**


