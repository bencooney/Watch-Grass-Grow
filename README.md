# Watch-Grass-Grow
For all the people who would rather watch grass grow than do something else. 


## Repo Fork Notes
This is a fork of jameszah's project @ https://github.com/jameszah/ESP32-CAM-Video-Recorder

jameszah/ESP32-CAM-Video-Recorder (and this repo by extension) is licensed under the GNU General Public License v3.0

I've created this divergence to customise the utility for my needs as a time lapse camera for my plants.

## How To...
1. Acquire ESP32-CAM hardware 
1. Obtain FTDI Programmer hardware for USB -> Serial communications
1. Install Arduino IDE
1. Add additional boards for ESP
1. Tweak settings for your network
1. Adjust video settings for desired video quality and frame-rates
1. Wire up the ESP32 for firmware uploading
1. Program.
1. Connect
1. Start Capture
1. Download video

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




