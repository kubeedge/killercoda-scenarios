# Identity Management Using SPIRE for Kubeedge

## Background

Security is a paramount requirement for edge computing architecture as security breaches can make a complete organization to come to a halt (IIot) , data breach can lead to privacy issues and also control of the complete edge computing infrastructure.

To enable better security, following needs to be satisfied for kubeedge framework
* Only verified and authorized edge nodes should be able to join cluster and connect to cloud.
* Applications connecting to edge computing framework should be verified against the assigned identities.
* Applications should be authorized to send and receive data from edge computing framework.
* Certificate rotation should be possible at each service-level.
* Audit at service-level for all communciation between services.

## SPIFFE and SPIRE

The Secure Production Identity Framework For Everyone (SPIFFE) Project defines a framework and set of standards for identifying and securing communications between services.
SPIFFE enables enterprises to transform their security posture from just protecting the edge to consistently securing all inter-service communications deep within their applications.
SPIFFE recommends industry standards like TLS and JWT for forming a identity document for every service. The service-level identity AuthN and AuthZ removes the dependency of complex network-level ACL strategies.

SPIRE (SPIFFE Runtime Environment) is a reference implementation of SPIFFE specification. SPIRE manages identities for node and workloads.
 It provides API for controlling attestation policies and identity issuance and rotation strategies.

More information about SPIRE can be found at [*https://github.com/spiffe/spire*](https://github.com/spiffe/spire).

## Benefits

* Node attestation: Only verifiable edge nodes can join the edge clusters. Every node is issued an identity on verification.
 In case of failed node attestations, no identity documents can be issued for services running on the node.

* Workload attestation: Only verifiable workload can run on edge nodes. In case of failed workload attestations, there are no identities issues for the workloads.
All communications are blocked from unverified workloads.

* Certificate rotation: Short-lived certificates are generated and rotation policies can be configured for every service communication.
There is no need for custom agents and reliance on specific orchestrators for certificate rotation configuration and management.

* Automated non-root CA certificate heirarchical deployments: Edge spire servers can be configured to not share any root CA chain for downstream nodes and workloads.

## SPIRE-based Identity Management Reference Architecture

Goal of this example is to achieve workload identity management for
cloud and edge processes . A reference architecture is shown below. A
list of things to-do is listed below in version information section.
For further integration , an extension add-on will be developed
integrated with kubeege for the same.


## Functional sequence diagrams

### Cloud component sequence
1\. Start cloud spire server.

2\. Generate token for node with spiffeID association for cloud node. (e.g: spiffe id = spiffe://example.org/upstream-cloud-node).

3\. Start spire agent with generated token. Node attestation is performed.

4\. Create entry with cloud spire server for cloud component (cloudapp in this example). The entry is associated with node spiffeID and selectors used for attestation of cloud component.

5\. Start spiffe-helper with helper.conf configuration. Spiffe-helper fetches certificates and starts ghostunnel. Spiffe-helper also updates the certificates and signals (SIGUSR1) to ghostunnel to reload certificates. Workload attestation is performed.

6\. Start cloud component. Cloud component uses localhost ip and port to transfer data. Ghostunnel fetches data from this port and securely sends the data to peer ghostunnel.

7\. SpiffeIDs are validated by ghostunnel to control authorization by using tls peer verification method. Authorized spiffeID are configured as arguments to ghostunnel in helper.conf.


### Edge component sequence

1\. Generate token for edge with spiffeID association for edge node. (e.g:spiffe id = spiffe://example.org/upstream-edge-node).

2\. Start spire agent (cloud spire agent) on edge node with configuration to connect to cloud spire server and associated token. Node attestation is performed.

3\. Create entry with cloud spire server for edge component. The entry is associated with node spiffeID and selectors used for attestation of edge component.

4\. Start edge spire server. Edge spire server starts with upstreamCA configured to cloud spire server.

5\. Edge spire server fetches certificate from cloud spire agent (running on edge node) which invokes workload attestation and receives workload certificates in response.

6\. Edge spire server connects to cloud spire server using workload certificates to fetch intermediate CA using spire node api.

7\. Generate token for edge with spiffeID association for edge node. (e.g:spiffe id = spiffe://example.org/downstream-edge-node).

8\. Start edge spire agent on edge node with configuration to connect to edge spire server and associated token. Node attestation is performed.

9\. Start spiffe-helper. Spiffe-helper fetches workload certificate for edge component (edge-hub) from cloud spire agent (running on edge node) and starts ghostunnel. Spiffe-helper also updates the certificates and signals (SIGUSR1) to ghostunnel to reload certificates. Workload attestation is performed.

10\. Start edge-hub (execute edge_core binary). Edge-hub uses localhost ip and port to transfer data. Ghostunnel fetches data from this port and securely sends the data to peer ghostunnel.

11\. SpiffeIDs are validated by ghostunnel to control authorization by using tls peer verification method. Authorized spiffeID are configured as arguments to ghostunnel in helper.conf.


### Edge application sequence

1\. Create entry with edge spire server for edge applications (eventbus and lightmapper in this example). The entry is associated with edge node spiffeID (token parameter used to register edge spire agent) and selectors used for attestation of edge application.

2\. Start spiffe-helper with helper.conf configuration (refer event-bus-helper.conf/user-app-helper.conf files). Spiffe-helper fetches certificates and starts ghostunnel. Spiffe-helper also updates the certificates and signals (SIGUSR1) to ghostunnel to reload certificates. Workload attestation is performed.

3\. Start edge applications. Edge application uses localhost ip and port to transfer data. Ghostunnel fetches data from this port and securely sends the data to peer ghostunnel.

4\. SpiffeIDs are validated by ghostunnel to control authorization by using tls peer verification method. Authorized spiffeID are configured as arguments to ghostunnel in helper.conf.


## Source Folders
* release : Directory has configurations and scripts to be used for deployment of identity management infrastructure for Kubeedge.

* app-agent-conf  : Configurations for spire agent interfacing with edge (event-bus) and user applications . Spire agent communicates to edge spire server.

* conf : Configurations for spire server (cloud and edge) and spire agent (agent communicating to cloud spire server).

* certs : Spiffe helper communicates with spire agents and download certificates in this folder . Ghostunnel is loaded with these certificates . For edge to user interface application , spiffe helper configuration and ghostunnel certs are present in event-bus and user-app folders respectively.

* app-binaries : All binaries for edge , cloud and test applications.

* log : Logs for different processes run as part of the example.

## Scripts
* deploy-cloud.sh : Deploys cloud part of identity management infrastructure. Used to

                    1) Start cloud spire server.
                    2) Registers cloud node and cloud agent.
                    3) Registers and starts cloud hub (test cloud hub command simulator).

* deploy-edge.sh  : Deploys edge part of identity management infrastructure.

                    1) Registers edge node and edge agent communication with cloud spire server.
                    2) Registers and starts edge spire server.
                    3) Registers and starts edge agent for edge to user app communication interface.

* start-spiffe-helper.sh  : Based on the configuration (helper.conf) , starts spiffe-helper communication for certificate download and rotation. Ghostunnel is run using spiffe-helper.
* commands.sh  : Abstracts spire cli commands.

