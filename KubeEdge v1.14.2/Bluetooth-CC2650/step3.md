## Please ensure that bluetooth service of your device is ON

#### Set 'bluetooth=true' label for the node (This label is a prerequisite for the scheduler to schedule bluetooth_mapper pod on the node [which meets the hardware / software prerequisites] )

```
kubectl label nodes <your-edge-node-name> bluetooth=true
```