# raspberrypi

Repository to store software, configurations and settings for developing video-enabled applications on Raspberry Pi.

This currently includes the `Livebulb` concept - a lightbulb-like device with livestreaming capabilities.

For some insights into the `Livebulb`, read [this issue](https://github.com/videoDAC/raspberrypi/issues/4).

To set up a livebulb, run these steps on a raspberrypi zero w:

1. Mount a Raspbian 10 (Buster) Lite image to a SD card

2. Add these files to the `boot` partition

 - [`ssh`](https://raw.githubusercontent.com/videoDAC/raspberrypi/master/config/ssh)
 - [wpa_supplicant.conf]()

Connect to the raspberrypi via `ssh`

Enable the camera by running the following command and using the GUI to enable the camera
```
sudo raspi-config
```
Then run the following commands
```
sudo apt update
sudo apt upgrade
sudo apt install ffmpeg
wget https://raw.githubusercontent.com/videoDAC/raspberrypi/master/systemd/livecam.service
sudo mv livecam.service /etc/systemd/system
sudo systemctl enable /etc/systemd/system/livecam.service
sudo reboot
```
