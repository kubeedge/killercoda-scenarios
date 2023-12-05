## Configurations Used
### Cloud node configuration

*Upstream CA – Cloud spire server configuration:*
&lt;SPIRE\_PATH&gt;/conf/server/server.conf

*Upstream CA Agent – Cloud node agent configuration :*
&lt;SPIRE\_PATH&gt;/conf/agent/agent.conf

Following fields might require modification based on the deployment environment

    bind_address = "192.168.56.101" <Cloud node vm IP>
    server_address = "192.168.56.101" <Cloud Spire Server IP>
    server_port = "8081" <Cloud Spire Server port>
    socket_path =/tmp/agent.sock"

### Edge node configuration

*Edge agent configuration to **connect to cloud spire server** :*
&lt;SPIRE\_PATH&gt;/conf/agent/agent.conf

Following fields might require modification based on the deployment environment

    bind_address = "192.168.56.102"
    bind_port = "8088"
    data_dir = "./.data"
    server_address = "192.168.56.101" // <Cloud spire server IP>
    server_port = "8081" // <Cloud spire server port>
    socket_path ="/tmp/upstream_agent.sock"

*Edge spire server configuration :*
&lt;SPIRE\_PATH&gt;/conf/server/server.conf

    UpstreamCA "spire" {
    plugin_data {
      server_address = "192.168.56.101" // <Cloud spire server IP>
      server_port = 8081 // <Cloud spire server port>
      workload_api_socket = "/tmp/upstream\_agent.sock"
    }

*Edge application agent configuration to connect to edge spire server :
&lt;SPIRE\_PATH&gt;/conf/app-agent-conf/agent/agent.conf*

    bind_address = "192.168.56.102"
    bind_port = "9088"
    data_dir = "./.app-data"
    server_address = "192.168.56.102" // <Edge spire server IP>
    server_port = "8081" // <Edge spire server port>
    socket_path ="/tmp/app-agent.sock"

### Spiffe helper configuration (IMPORTANT)

Spiffe helper is used to execute ghostunnel for creating communciation
channel over TLS for cloud , edge and user workloads . Please refer to
the specific configurations in the folders section.

All the helper configurations need to be updated with IP addresses and
ports as per the deployment in

1\. &lt;SPIRE\_PATH&gt;/helper.conf

2\. &lt;SPIRE\_PATH&gt;/event-bus/event-bus-helper.conf

3\. &lt;SPIRE\_PATH&gt;/user-app/user-app-helper.conf

In the list of To-Dos , there is an item to generate these
configurations automatically based on environment configuration to avoid
errors.

Following is a sample configuration for kubeedge event-bus interface which invokes ghostunnel in server mode:
```
    agentAddress = "/tmp/app-agent.sock"
    cmdArgs = "**server** --listen 192.168.56.102:18884 --target 127.0.0.1:2884 --cacert /opt/spire/event-bus/certs/svid\_bundle.pem --keystore /opt/spire/event-bus/certs/new\_bundle.p12 **--allow-uri-san spiffe://example.org/downstream-app-event-bus**"
    cmd = "/opt/spire/ghostunnel"
    certDir = "/opt/spire/event-bus/certs"
    renewSignal = "SIGUSR1"
    svidFileName = "svid.pem"
    svidKeyFileName = "svid\_key.pem"
    svidBundleFileName = "svid\_bundle.pem"
```
Following is a sample configuration for user-app interface which invokes ghostunnel in client mode:
```
    agentAddress = "/tmp/app-agent.sock"
    cmdArgs = "client --listen 127.0.0.1:1884 --target 192.168.56.102:18884 --cacert /opt/spire/user-app/certs/svid_bundle.pem --keystore /opt/spire/user-app/certs/new_bundle.p12 --verify-spiffe-id spiffe://example.org/downstream-app-event-bus"
    cmd = "/opt/spire/ghostunnel"
    certDir = "/opt/spire/user-app/certs"
    renewSignal = "SIGUSR1"
    svidFileName = "svid.pem"
    svidKeyFileName = "svid_key.pem"
    svidBundleFileName = "svid_bundle.pem"
```

