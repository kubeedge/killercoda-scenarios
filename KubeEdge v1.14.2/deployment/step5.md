# Setup edgecore(on Edge Node)

In Kubernetes 1.23 and earlier, you could use Docker Engine with Kubernetes, relying on a built-in component of Kubernetes named dockershim. The dockershim component was removed in the Kubernetes 1.24 release; however, a third-party replacement, cri-dockerd, is available. The cri-dockerd adapter lets you use Docker Engine through the Container Runtime Interface.

### Setup cri-dockerd 

``` 
wget https://github.com/Mirantis/cri-dockerd/releases/download/v0.3.4/cri-dockerd-0.3.4.amd64.tgz
tar -xvf cri-dockerd-0.3.4.amd64.tgz
cd cri-dockerd/
mkdir -p /usr/local/bin
install -o root -g root -m 0755 ./cri-dockerd /usr/local/bin/cri-dockerd

```{{execute}}

### Add the files cri-docker.socker cri-docker.service

```
sudo tee /etc/systemd/system/cri-docker.service << EOF
[Unit]
Description=CRI Interface for Docker Application Container Engine
Documentation=https://docs.mirantis.com
After=network-online.target firewalld.service docker.service
Wants=network-online.target
Requires=cri-docker.socket
[Service]
Type=notify
ExecStart=/usr/local/bin/cri-dockerd --container-runtime-endpoint fd:// --network-plugin=
ExecReload=/bin/kill -s HUP $MAINPID
TimeoutSec=0
RestartSec=2
Restart=always
StartLimitBurst=3
StartLimitInterval=60s
LimitNOFILE=infinity
LimitNPROC=infinity
LimitCORE=infinity
TasksMax=infinity
Delegate=yes
KillMode=process
[Install]
WantedBy=multi-user.target
EOF

sudo tee /etc/systemd/system/cri-docker.socket << EOF
[Unit]
Description=CRI Docker Socket for the API
PartOf=cri-docker.service
[Socket]
ListenStream=%t/cri-dockerd.sock
SocketMode=0660
SocketUser=root
SocketGroup=docker
[Install]
WantedBy=sockets.target
EOF


```{{execute}}

### Daemon reload

```
systemctl daemon-reload
systemctl enable cri-docker.service
systemctl enable --now cri-docker.socket
systemctl start cri-docker.service

```{{execute}}



