# Change some configs
<br>
In this step, we are going to change some config.

<br>
<br>
Open the file using following command, and add the comment line.   

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

Open the file using following command, and modify the comment line.   

`vi /etc/kubeedge/config/edgecore.yaml`{{execute}}    

```
edged:  
    cgroupDriver: systemd               # change from 'cgroupf' to 'systemd'  
    cgroupRoot: ""  
    cgroupsPerQOS: true
```{{}} 
<br>
<br>

Reload the edgecore.    

`systemctl daemon-reload && sudo systemctl enable edgecore && sudo systemctl start edgecore`{{execute}}
