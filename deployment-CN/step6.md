# 修改部分配置
<br>
在此步骤中，我们将修改部分配置。

<br>
<br>
使用提供的命令行打开文件, 并增加注释行。

`vi /etc/systemd/system/edgecore.service`{{execute}}  

```
[Service]  
Environment=CHECK_EDGECORE_ENVIRONMENT='false'         # add this line   
Type=simple  
ExecStart=/usr/local/bin/edgecore  
Restart=always  
RestartSec=10
```{{}}     
<br>

使用提供的命令行打开文件, 并修改注释行。  

`vi /etc/kubeedge/config/edgecore.yaml`{{execute}}    

```
edged:  
    cgroupDriver: systemd               # change from 'cgroupf' to 'systemd'  
    cgroupRoot: ""  
    cgroupsPerQOS: true
```{{}} 
<br>
<br>

重新加载edgecore。     

`systemctl daemon-reload && sudo systemctl enable edgecore && sudo systemctl start edgecore`{{execute}}
