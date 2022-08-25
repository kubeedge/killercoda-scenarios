# 创建边缘节点
<br>
执行keadm gettoken命令，返回的token值将在下一步中用到。将返回值保存在变量token_value中。

`token_value=$(keadm gettoken)`{{execute}}
<br>
<br>
接下来, 使用keadm join命令安装边缘节点，并通过参数设置将边缘节点纳入cloudcore的管理。
  
`keadm join --cloudcore-ipport=172.30.1.2:10000 --token=${token_value}`{{execute}}  

--cloudcore-ipport是必选参数，应与cloudcore的advertise-address保持一致；     
--token值为上一步的返回值。
<br> 
<br>
**现在你可以看到KubeEdge的edgecore已被成功创建。**

