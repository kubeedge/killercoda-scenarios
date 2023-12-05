### Run the track player app
- Copy the trackplayer binary to the rpi. Make sure the MQTT broker is running on the rpi.
  Run the binary. The app will subscribe to the `$hw/events/device/speaker-01/twin/update/document` topic
  and when it receives the desired track on the topic, it will play it on the speaker.

```
./trackplayer
```