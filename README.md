# LoRa-Arduino quickstart project

![](assets/schema-LoRa-Arduino-1.png)

# Overview
###This project allows you to quickly try LoRa communications. 
**LoRa** is an exciting new technology for communicating at **Lo**ng **Ra**nge, low power, and low cost.  This project sends data from an Arduino Uno and a [Multitech mDot LoRa node](http://www.multitech.com/models/94557148LF) to the [Senet LoRa network](https://app.senetco.com/senetdev/login.aspx). Senet's JSON data payloads are converted by [Zapier](https://zapier.com) into data rows in a Google Spreadsheet. 

This project was developed by the [Orange IoT Studio](http://orangeiotstudio.com/) to promote the consideration and adoption of LoRa. To that end, the IoT Studio is [supporting companies](http://orangeiotstudio.com/) interested in LoRa by lending out hardware kits and by funding co-development.  

This project should take about an hour to complete, once you have the hardware.

![](assets/Kit_schema-02.png)

### LoRa is great for IoT
LoRa is an ideal communications technology for many internet-of-things (IoT) devices because **internet connectivity** is a key feature of IoT but also one of IoT devices' the biggest burdens.  Specifically, pairing devices with WiFi or Bluetooth is tedious; cellular connectivity is easy to implement and can transmit megabytes (MB) of data, but its often not affordable for simple IoT devices.  For simple IoT devices that only need to send kilobytes (KB) of data or less, LoRa is an ideal solution.  

Public LoRa networks are being deployed world wide, including by [Orange in France](http://www.orange.com/en/Press-and-medias/press-releases-2016/press-releases-2015/Orange-deploys-a-network-for-the-Internet-of-Things). This project uses the [Senet LoRa network](https://app.senetco.com/senetdev/login.aspx) in North America since it was developed by the [Orange IoT Studio](http://orangeiotstudio.com/), part of [Orange Silicon Valley](http://orangesv.com/) in San Francisco. 

### Project overview  
1. Get the hardware 
2. Get the software
3. Verify LoRa coverage
4. Configure the software
5. Assemble the hardware 
6. Test drive LoRa
7. Build on LoRa & promote your vision
 
### _Disclaimer_
_LoRa is a new technology and this project is in alpha, so it could break. If you're cool trying new things that aren't 100% reliable, proceed and have fun._   


## Get the hardware
You'll need to either purchase the equipment yourself or apply for a hardware kit from the IoT studio. 

### Apply for support from the IoT Studio
The IoT Studio is [supporting the developer community](http://orangeiotstudio.com/) to encourage use of LoRa.  You can apply to borrow a hardware kit containing the bill of materials, below. If you work for a company with a compelling use case, you can also apply for funded co-development.  



### Bill of Materials (BOM)
You'll need one (1) of each item below, unless otherwise noted. The prices are estimates.

####Basic equipment  

* [Multitech mDot](http://www.digikey.com/product-search/en?mpart=MTDOT-915-X1P-SMA-1&v=591&v=881),  $60 
* [Arduino Uno](https://www.sparkfun.com/products/11021),  $25 
* [XBee shield](http://www.robotmesh.com/xbee-shield-v2-0),  $10   
* [Antenna for mDot](http://www.digikey.com/product-detail/en/multi-tech-systems/AN868-915A-10HRA/881-1242-ND/5246371), $10
* [USB Type-A cable](https://www.adafruit.com/products/62), $4
* [mDOT USB developer board](http://www.multitech.com/brands/micro-mdot-devkit), _??get link with price!_
* [Wires](https://www.adafruit.com/products/1956), $2 (you'll need 6 male-male wires)
* [Semtech NorAm mote LoRa network tester](http://www.semtech.com/images/datasheet/NorAmMote_User_Guide_3v0.2.pdf), _??get link with price!_	

####LittleBits sensors are easier to use, but more expensive.  
* [LittleBits Proto](https://littlebits.cc/bits/proto), $50 (you'll need 4 Protos at $12/piece)
* [LittleBits Fork](https://littlebits.cc/bits/fork), $12
* [LittleBits Sound trigger](http://littlebits.cc/bits/sound-trigger), $12
* [LittleBits Light sensor](http://littlebits.cc/bits/light-sensor), $12
* [LittleBits Button](http://littlebits.cc/bits/button), $8
* [LittleBits LED](http://littlebits.cc/bits/led), $8
 

####Sparkfun sensors require more work, but are more affordable. 
_Mike & Anna need to try this!!_

* [Breadboard](https://www.adafruit.com/products/64), $5
* [Sound trigger](??), _??get link with price!_ 
* [Light sensor - Photo transistor](https://www.adafruit.com/products/2831), $0.95
* [Tactile Button switch ](https://www.adafruit.com/products/367), $2.5
* [LED](https://www.adafruit.com/products/299), $4

## Get the software

### Create your accounts
You'll need to create accounts with the following websites to get this project to work.  

### Senet
[Senet](https://app.senetco.com/senetdev/login.aspx) provides a public LoRa network in North America. They're contining to increase coverage around the United States, but there's a chance you might not have coverage at your workbench. 
You so you can use a NorAm mote to determine whether you have coverage in your area.
### Zapier
[Zapier](https://zapier.com) automates the flow of data between Senet and Google Docs. 
### Google Drive
If you don't have a Google account, wow ;) You'll need [Google Spreadsheets](https://docs.google.com/spreadsheets/u/0/) to view and analyze your data in this project.


## Verify LoRa coverage 
[Senet](https://app.senetco.com/senetdev/login.aspx) provides a public LoRa network in North America. There's a chance you might not have coverage at your workbench, but that you do have coverage nearby. 

You can use a NorAm mote to determine where you have coverage.  In some cases


  
*Anna to make graphic of NorAm mote with GPS coming in and LoRa going out .*

*include photo of the NorAm mote*

*include link to sample gdoc w/ proper formulas from PDU to Lat/Long*

*include video with Mike explaining our NorAm mote*

   
## Configure the software

### mDot 
AT commands  
9600 baud  
Drag & Drop in MacBook. If Windows is different, please let us know how you loaded the mDot firmware and we'll update the instructions here. 

### Adruino Uno
You'll need the Arduino IDE. 

**You must customize your Arduino code so that it works with your mDot**

`/* AAA with ID ending in 11:22 */     const String mDot_name = "AAA"; const String Network_key =  "11:22:33:44:55:11:22:33:44:55:11:22:33:44:11:22"; const String Network_ID = "11:22:33:44:55";` 

*show cassis and how we labeled the mDot and tied the device # to the name*

These two files allow an Arduino to communicate via LoRa.  To reduce the dynamic memory of this sketch, reduce or remove the text in the Serial.print() statements.  The .ino file is for the Arduino.  The .bin file is for the Multitech mDot LoRa node. The sketch gathers sensor data to demonstrate *LoRa* by indicating activities in the kitchen: 
 1. Click. Count how many times users click a button. 
 2. Sound. Count how many times there's a loud noise.  
 3. Light. Meausre the average light level. 

## Assemble the hardware 
Plug stuff in to match the photo

## Test drive LoRa
Power up and run it!
Let us know that it worked

## Build on LoRa, Promote your vision
We hope that you'll use this project 
Share your experience -- we're featuring the most interesting projects on our website.

## Acknolwedgements

Mike Vladimer & Anna Aflalo developed this project at the [Orange IoT Studio](http://orangeiotstudio.com), part of [Orange Silicon Valley](http://www.orangesv.com/). We welcome feedback -- you can contact us via twitter: [@orangeiotstudio](https://twitter.com/orangeiotstudio), 
 [@mikevladimer](https://twitter.com/mikevladimer) & [@anna_aflalo](https://twitter.com/anna_aflalo).  
**Thanks to** Dave Kjendal & Shaun Nelson @ Senet, Joe Knapp @ Semtech. 
 
April 2016 

