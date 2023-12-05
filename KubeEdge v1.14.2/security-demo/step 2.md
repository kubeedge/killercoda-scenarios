## How to test device application

1\. Following hack needs to be used as v0.2 does not support device deployment using kubectl.
Kill edgecontroller process in cloudvm. Execute cloud-app application located at $SPIRE_PATH/app-binaries/cloud/ folder.

2\. Register an example device with cloud using following command. Please
note, in the current version, cloud test application opens 30000 port
for metadata creation (create pod or device) and 20000 port for
communication with kubeedge edgehub. In cloud node, execute

```
curl -XGET http://127.0.0.1:30000/device -H 'content-type:application/json' -d@/opt/spire/app-binaries/cloud/test-device.yaml
```

3\. Run the light\_mapper application from app\_binaries in edge node. Light mapper
application is a binary built from
[*https://github.com/kubeedge/examples/tree/master/led-raspberrypi*](https://github.com/kubeedge/examples/tree/master/led-raspberrypi).
Usage of the application can be referred in the same page.

For spire server cli usage , please refer to
[*https://github.com/spiffe/spire*](https://github.com/spiffe/spire).