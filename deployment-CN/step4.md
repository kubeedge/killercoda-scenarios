# 创建云端节点
<br>
使用下方的命令安装cloudcore。    

--advertise-address是非必选参数，为云端暴露的地址（将添加到CloudCore证书的SAN中），默认值为本地IP。    

`keadm init --advertise-address=172.30.1.2`{{execute}}

**现在你可以看到KubeEdge的cloudcore已被成功创建。**
