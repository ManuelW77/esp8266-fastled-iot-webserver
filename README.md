# ESP8266 FastLED IoT Webserver

<a href="https://github.com/NimmLor/esp8266-nanoleaf-webserver/graphs/contributors" alt="Contributors">
        <img src="https://img.shields.io/github/contributors/NimmLor/esp8266-nanoleaf-webserver" /></a>

This is a fork of [jasoncoon's esp8266 fastled webserver](https://github.com/jasoncoon/esp8266-fastled-webserver) that was adapted to control the colors of my  [LED-Projects](https://www.thingiverse.com/Surrbradl08/designs).



**New:** Windows application to sync the LED devices with music. Completely optional but it's awesome. But it's just the first prototype and very experimental. Software and docs still work in progress.

https://github.com/NimmLor/IoT-Audio-Visualization-Center 



Can be downloaded [here](https://github.com/NimmLor/IoT-Audio-Visualization-Center/releases).

![screenshot_alpha](C:\Repos\esp8266-fastled-iot-webserver\screenshot_alpha.jpg)

https://github.com/NimmLor/IoT-Audio-Visualization-Center



## What happened here?

All of my recent project were merged into one including most of the features. A new and optional Windows application allows to sync the LEDs to a Windows audio source of your choice.



### Supported Devices

**Generic LED-Strip**, just a regular LED-Strip without special hardware

  * Easiest: 5V WS2812B LED-Strip:		https://s.click.aliexpress.com/e/_dZ1hCJ7
  * (Long Ranges) 12V WS2811 LED-Strip:	https://s.click.aliexpress.com/e/_d7Ehe3L
  * (High-Speed) 5V SK9822 LED-Strip:		https://s.click.aliexpress.com/e/_d8pzc89
  * (Expensive) 5V APA102 LED-Strip:		https://s.click.aliexpress.com/e/_Bf9wVZUD
  * (Flexible) 5V WS2812 S LED-Strip:		https://s.click.aliexpress.com/e/_d6XxPOH
  * Wemos D1 Mini:						https://s.click.aliexpress.com/e/_dTVGMGl
  * 5V Power Supply:						https://s.click.aliexpress.com/e/_dY5zCWt
  * Solderless LED-Connector:				https://s.click.aliexpress.com/e/_dV4rsjF
  * 3D-Printed Wemos-D1 case:				https://www.thingiverse.com/thing:3544576

**LED-Matrix**, with a flexible LED-Matrix you can display the audio like a Audio Visualizer
* Flexible WS2812 Matrix:				https://s.click.aliexpress.com/e/_d84R5kp
	
* Wemos D1 Mini:						https://s.click.aliexpress.com/e/_dTVGMGl
	
* 5V Power Supply:						https://s.click.aliexpress.com/e/_dY5zCWt
	

**3D-Printed 7-Segment Clock**, display the time, syncs with a ntp server of your choice

* unfortunately the "thing's" description isn't updated yet to the new standalone system
	
* Project link, small version:			https://www.thingiverse.com/thing:3117494
	
* Project link, large version:			https://www.thingiverse.com/thing:2968056

**3D-Printed Desk Lamp**, a Lamp that reacts to sound for your desk

* Project link, twisted version:		https://www.thingiverse.com/thing:4129249
* Project link, round version:			https://www.thingiverse.com/thing:3676533

**3D-Printed Nanoleafs**, a Nanoleaf clone that can be made for cheap

* Project link:													https://www.thingiverse.com/thing:3354082
	
* 5: 3D-Printed Animated RGB Logos
	
* Project link, Twenty-One-Pilots Logo:		https://www.thingiverse.com/thing:3523487
	
* Project link, Thingiverse Logo:			https://www.thingiverse.com/thing:3531086



## Changelog

### 07.05.2020, Major Code rewrite and merge of projects, audio visualization

- **New features:**
  - **Audio Visualization with a Windows Desktop Application (C#, WPF)** [here](https://github.com/NimmLor/IoT-Audio-Visualization-Center)
  - multicast DNS by @WarDrake
  - OTA Support
  - MQTT/Homeassistant integration by @WarDrake
  - Serial Ambilight for usage behind a TV
  - Support of Desk Lamp, 7-Segment Clock, Animated RGB Logos, Generic LED-Strip

### 01.02.2020, Native Alexa Update

- **NodeRED** part is now **DEPRECATED**
- The Nanoleaf Replica allows now for **NATIVE** Alexa support without the need of an extra Raspberry Pi. When added to the Smart Home devices in the Alexa app, the nanoleafs will appear as Phillips Hue devices.
- Added Strobe Pattern
- Added Sound Reactive support
- Some code cleanup and new parameters to configure
- New step by step installation instructions ([Software_Installation.md](Software_Installation.md))



### 24.02.2019, NodeRED Update (Depricated)

- Node-RED integration was added
- Alexa support via NodeRED



### Bill of Materials

- 1x [Wemos D1 mini](http://s.click.aliexpress.com/e/_srb2XX) is recommended, but any other ESP8266 variant should work too, but it might require an additional step-down converter.
- [WS2812B LED Strip **IP30**](http://s.click.aliexpress.com/e/_sUwhA1), only IP30 will fit inside the nanoleafs, I'll recommend at least 60LEDs/m
- 1x [Microphone Sensor](http://s.click.aliexpress.com/e/_sYiUrz) (Optional), MAX4466 Sensor is recommended
- 1x [3.3V to 5V Logic Level Shifter](http://s.click.aliexpress.com/e/_s49Saz) (optional, required if LEDs "glitch")
- 1x [Female Power Jack](http://s.click.aliexpress.com/e/_sPe0RR)
- 1x [5V Power Supply](http://s.click.aliexpress.com/e/_sIzXbC), Note: 100 LEDs draw around 4A



Hardware
--------

**Check out the project on [Thingiverse](https://www.thingiverse.com/thing:3354082) for more details.**

[![https://www.thingiverse.com/Surrbradl08/things](https://cdn.thingiverse.com/site/img/thingiverse-logo-2015.png)](https://www.thingiverse.com/thing:3354082)




Installation
--------
**FOR INSTALLATION REFER TO THE [Software_Installation.md](Software_Installation.md)**



Features
--------
* Turn the LEDs on and off
* Appear as an **ALEXA SMART HOME DEVICE**
* **Sound Reactive Mode**
* Adjust the brightness, color and patterns
* Play over 30+ patterns in Autoplay





Web App
--------

![Webinterface](https://github.com/NimmLor/esp8266-nanoleaf-webserver/blob/master/gallery/interface.jpg?raw=true)

The web app is stored in SPIFFS (on-board flash memory).



## Circuit

![circuit without Logic level converter](wiring.jpg)



## Technical

Patterns are requested by the app from the ESP8266, so as new patterns are added, they're automatically listed in the app.

The web app is stored in SPIFFS (on-board flash memory).

The web app is a single page app that uses [jQuery](https://jquery.com) and [Bootstrap](http://getbootstrap.com).  It has buttons for On/Off, a slider for brightness, a pattern selector, and a color picker (using [jQuery MiniColors](http://labs.abeautifulsite.net/jquery-minicolors)).  Event handlers for the controls are wired up, so you don't have to click a 'Send' button after making changes.  The brightness slider and the color picker use a delayed event handler, to prevent from flooding the ESP8266 web server with too many requests too quickly.

The only drawback to SPIFFS that I've found so far is uploading the files can be extremely slow, requiring several minutes, sometimes regardless of how large the files are.  It can be so slow that I've been just developing the web app and debugging locally on my desktop (with a hard-coded IP for the ESP8266), before uploading to SPIFFS and testing on the ESP8266.



### Alexa

The code has an optional feature to be able to control the lamp via Alexa on any Amazon Echo device. For setup instructions refer to [Software_Installation.md](https://github.com/NimmLor/esp8266-fastled-desk-light/blob/master/Software_Installation.md) document.



### Compression

The web app files can be gzip compressed before uploading to SPIFFS by running the following command:

`gzip -r data/`

The ESP8266WebServer will automatically serve any .gz file.  The file index.htm.gz will get served as index.htm, with the content-encoding header set to gzip, so the browser knows to decompress it.  The ESP8266WebServer doesn't seem to like the Glyphicon fonts gzipped, though, so I decompress them with this command:

`gunzip -r data/fonts/`

### REST Web services

The firmware implements basic [RESTful web services](https://en.wikipedia.org/wiki/Representational_state_transfer) using the ESP8266WebServer library.  Current values are requested with HTTP GETs, and values are set with POSTs using query string parameters.  It can run in connected or standalone access point modes.

