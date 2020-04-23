# Watch-Grass-Grow
For all the people who would rather watch grass grow than do something else. 


## Repo Fork Notes
This is a fork of jameszah's project @ https://github.com/jameszah/ESP32-CAM-Video-Recorder

jameszah/ESP32-CAM-Video-Recorder (and this repo by extension) is licensed under the GNU General Public License v3.0

I've created this divergence to customise the utility for my needs as a time lapse camera for my plants.

## Using this firmware
### Prerequisites 
#### Acquire ESP32-CAM hardware 
This firmware is written for the ESP32-CAM hardware. A very cheap camera intended for DIY and prototyping. This includes built-in Wifi, TF (MicroSD) Card, and camera.
  
#### Obtain FTDI Programmer hardware for USB -> Serial communications
To flash your ESP32-CAM with this firmware you'll need a USB-to-Serial programmer. This is a small USB dongle with header-pins for: Power (V+/VCC), Ground (G), Transmit (Tx), Receive (Rx)

Most programmer dongles will allow you to switch between 3.3v and 5v. Either by a switch or by seperate pins for the two voltages. While the ESP32 can apparently be used on 3.3v, I recommend using the 5v.

Some USB-to-Serial programmers will have additional pins. Those can be ignored for this usecase.

#### Install Arduino IDE
The ArduinoIDE is the ideal tool for working with this code and the ESP range of SoC. Because it can be used for editing, valdating code, and uploading the binary to the chip. 

Check [The Arduino Website](https://arduino.cc) for the best instructions on how to install the latest Arduino IDE for your OS.

On linux it's usually good enough to just install the repo package `sudo dnf install arduino` or `sudo apt install arduino`. However those versions are often significantly out of date.

#### Add additional boards for ESP
By default ArduinoIDE only supports Arduino boards. So once you have the Arduino IDE running you'll need to add support for the ESP boards. 

1. Open the *File* menu and choose *Preferences*
1. Find the setting for *Additional Boards Manager URLs:* 
1. Add the following URL to the list of URLs: `https://dl.espressif.com/dl/package_esp32_index.json`
1. Click *OK* and close the preferences screen
1. Open the *Tools* menu and hover your mouse over *Board: [abcdef]* - A board selector sub-menu should appear. 
1. Choose the *Boards Manager...* item
1. Filter the list by `esp32` - you should see 'esp32 by Espressif Systems'
1. Install the package (This code has been tested with 1.0.4. More recent versions should work, but avoid 1.0.2 as it's notorious for causing wifi problems.)

You should now be able to see a range of different ESP32 boards in the board selector sub-menu. 

Since you're working with the ESP-CAM, Choose **'AI thinker ESP32-CAM'**.



### Setup
Now you've done the pre-reqs. Time to get the project going..

#### Start editing
If you haven't already, clone this repo from github 

`git clone https://github.com/bencooney/Watch-Grass-Grow.git`

Launch ArduinoIDE and Open the 'Watch-Grass-Grow.ino' file.


#### Tweak settings for your network
The 'Watch-Grass-Grow' camera will connect to your wifi network. I strongly recommend users to keep IOT devices like this project on a seperate wifi network (+ v/lan network) and to use firewalls to limit access of the iot device.

The WiFi network needs to be a 2.4ghz type network.

Change the code to specify your wifi settings:

1. Search for 'IOT_WIFI_SSID'
1. Remove IOT_WIFI_SSID and Enter the name of your wifi network. 
1. In the next line do the same to enter your wifi network's password

#### Set FTP user and password
These will be required when downloading videos from your camera. 

1. Search for 'ftpSrv.begin' 
1. By default both the user and pass are set to 'esp' 
1. Choose whatever username and password you want to use.




#### Adjust video settings for desired video quality and frame-rates


#### Wire up the ESP32 for firmware uploading
#### Program.
#### Connect
#### Start Capture
#### Download video

## Tips
### Downloading Videos
Web browser may have issues downloading the videos. Use wget, curl or an ftp client to download videos. 

for example: `wget --user=esp --password=esp ftp://192.168.1.9/desklens_1970-01-01_00.00.57_uxga_Q10_I5000_L32000_S30.avi
`

### "Integrating" with Home Assistant 
You can imbed a photo of the current view from your camera using Home Assistant's *Picture Card* set the image path to the image capture link for your camera.

for example: **http://192.168.1.9/capture**

## TODO List
1. Finish this README
1. Automate HIDE PASSWORD before upload to github
1. Fix the max interval limit of ints - *done* (?maybe), moved interval to longs
1. Make 'darkmode' html
1. Add URL Generator for creating the start-command  
1. Add params for unit of time (i.e.: enable second/minutes/days as duration or interval)
1. Add script for wget/curl 
1. Add AP Mode and Config To Setup WiFi (Avoid hardcoded creds)
1. Add ability to ignore consecutive 'black' frames




