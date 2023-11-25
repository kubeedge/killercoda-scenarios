### Run PI Player App

Make sure the MQTT broker is running on the RaspBerry PI.
Copy the PI Player App binary to the RaspBerry PI and run it.
The App will subscribe to the `$hw/events/device/speaker-01/twin/update/document` topic
and when it receives the expected track on the topic, it will play it on the speaker.
At last, you need to copy the music files into the folder `/home/pi/music/` on the RaspBerry PI.
The music file name is like <track>.mp3, for example: `1.mp3`

The PI Player App will issue the `omxplayer` to play music,
please make sure the `omxplayer` is installed on the RaspBerry PI.
If not, please see the following link to setup `omxplayer`.

https://raspberry-projects.com/pi/software_utilities/media-players/omxplayer

```
./pi-player-app
```