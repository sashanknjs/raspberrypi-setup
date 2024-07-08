# raspberrypi-setup
This repository will help to setup a raspberry pi desktop from scratch and enable SSH and VNC for remote access of the raspberry pi wirelessly within your home network.

**Hardware:**
- Raspberry Pi any model works fine but preferably Raspberry Pi 3 or above with atleast 1GB RAM.
- SD Card (8GB or above)
- Power Adapter
- HDMI to HDMI cable (for Rasperry Pi 2,3 and 3B+) or Micro HDMI to HDMI (for Rasperry Pi 4 and 5)
- Ethernet cable
- USB Mouse and Keyboard
- Monitor (Display)

**OS:** Rasperry Pi OS - 32 or 64 bit (Desktop)

**Setup**
- Dowload the [Raspberry Pi Imager](https://www.raspberrypi.com/software/) on your PC. Once installed, connect the SD card to your PC and open the imager.

![image](https://github.com/sashanknjs/raspberrypi-vpn-server/assets/168824530/e4db8c6a-5a05-406c-83e6-2720833afc71)

- Before installing the OS, a few settings such as username and password, Wifi credentials and SSH options can be modified

![image](https://github.com/sashanknjs/raspberrypi-vpn-server/assets/168824530/e9278451-c6b4-411b-aae1-5f8c65a5fa55)

![image](https://github.com/sashanknjs/raspberrypi-vpn-server/assets/168824530/41914cf2-a0d2-46d8-9177-ee1bf1285c78)

- Once the OS in installed on the SD card, eject it from your PC and istall it onto the Raspberry Pi. Also, connect the Raspberry Pi to power and using the HDMI cable, connect it to a display.
- In case you did not enter the WIFI credentials or your device does not support WIFI, connect the Raspberry Pi to your WIFI router using the Ethernet cable.
- Connect the USB Mouse and Keyboard to the Raspberry Pi.

Once the OS is booted, the home screen will be visible as shown.

![image](https://github.com/sashanknjs/raspberrypi-setup/assets/168824530/e513b8c5-d506-419a-98c8-10ad4f250007)

**IP address**

The first thing to do after setting up your Raspberry Pi is to find its IP address. This is very important since it would be used to access the Raspberry Pi remotely. There are atleast two ways to find the IP address. 

- The first way is to open a terminal in the display connected to the Raspberry Pi and type the following command:

  ```
  ifconfig
  ```

![image](https://github.com/sashanknjs/raspberrypi-setup/assets/168824530/9ca9827e-55b6-4a62-9367-324eeb898b0f)


In case you are connected to a network using Ethernet, the value next to 'inet addr' within eth0 is the ip address. In case you are connected to a WIFI network, the value next to 'inet addr' within wlan0 is the ip address. I case you are connected to both, either off them can be used as the ip address.

- The second method is to login to your WIFI router by typing the ip adress of your home network (usually 192.168.1.1) in a browser in your PC. Once you enter the credentials, select the devices option which shows the list of the devices and their ip addresses connected to the network. From these devices, find the IP address of the Raspberry Pi.
  
**SSH setup**

SSH allows users to access the raspberry pi from a terminal of any PC within the home network. In case SSH was not enabled during the installlation of the OS, it can be done at this point. To do that, open a terminal and type
```
sudo raspi-config
```
This will open up a dialog box. 

![image](https://github.com/sashanknjs/raspberrypi-setup/assets/168824530/b3b75205-ec27-42f8-99b3-55a9b6101a3c)

- Select the Interface options.

![image](https://github.com/sashanknjs/raspberrypi-setup/assets/168824530/48a7c82a-03c6-41f4-b762-0bfbd08a060f)

- From here, select SSH and toggle it to ON. This will turn on the SSH server in the Raspberry Pi.

**To login to the Raspberry Pi remotely using SSH:**

- Open a terminal in your PC.
```
ssh username@ipaddress
```
Replace 'username' with the username of your raspberry pi used during the os installation and the 'ipaddress' with the ip address noted from the step shown above. When you enter is line, it will prompt you to enter the password. Once entered, you will successfully be logged in to the Raspberry Pi.

![image](https://github.com/sashanknjs/raspberrypi-setup/assets/168824530/abe89add-3d1c-40de-a5d4-e413f1869240)

**VNC setup**

VNC provides users to access the Raspberry Pi from a virtual desktop on any PC within the home network. Users can access the desktop of the Raspberry Pi wirelessly usinng VNC. 

To setup VNC on Raspberry Pi, open up a terminal once again and type sudo raspi-config and select Interface oprions.
Here, you will find VNC. Select that and toggle it to ON.

Now, on your host PC, download the RealVNC Viewer application from [here](https://www.realvnc.com/en/connect/download/viewer/?lai_sr=10-14&lai_sl=l). Once dowloaded and installed, open the application.

![image](https://github.com/sashanknjs/raspberrypi-setup/assets/168824530/9986c958-da0c-4bc5-aab0-daeb4057237a)

Now in the address bar, enter the ip address of your Raspberry Pi. This will open up a dialog box asking to enter the username and password. Once entered and connect option is clicked, you are successfully logged in to the Raspberry Pi and the Remote Desktop of the Raspberry Pi appears on the screen. 

