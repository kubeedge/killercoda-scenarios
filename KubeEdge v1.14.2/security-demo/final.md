## Present support

1\. Initial infrastructure deployment.

2\. 1-1 cloud and edge node. Multiple edge nodes are not supported in
scripts.

3\. Communication from user application and edge application using
certificates issued by cloud spire server and edge spire server.

4\. Supports kubeedge v1.5+.

## ToDo

1\. Optimization for redundancies in configuration and scripts.

2\. Test and support upstream\_bundle=false to prune rootCA at edge spire server.

3\. Trusted cloud spire server for communication between edge spire agents, edge spire server, cloud spire agent and cloud spire server.

4\. Secure communication between event bus and internal mqtt server.