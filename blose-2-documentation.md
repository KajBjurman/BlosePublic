# Documentation for Blose version 2

## About 

Blose is an app for watches running Wear OS. The intention of the app is to be able to
view current Glucose value on the watch, from a Dexcom or Libre sensor.

Blose is developed and maintained by Kaj Bjurman.

## Major changes

Version 2 of Blose requires at least Wear OS version 5.

Wear OS version 5 removed the possibility of having a watch face with code, which means
that Blose no longer can have a watch face built in. The watch faces have for that reason
been removed from Blose. 

Blose still has a tile, and can provide data to complications in watch faces that you download
separately. 

Configuration of Blose has changed a lot since there no longer is a built in watch face.

## Initial setup

Install Blose from Google play. Either through Google play on the watch, or by selecting
the compatible watch as target when you try to install using Google play on another device. 

### Dexcom

Blose can use Dexcom Share as a data source, but Dexcom sensors aren't uploading glucose
values to Dexcom Share by default. 

Sharing should already work if you have at least one follower, that can get data in the
Dexcom follow app. 

Perform the following steps, if you don't already have followers. 

* Open the Dexcom app on the main phone. Make sure that sharing is turned on. 
* Invite a follower. You can invite yourself. 
* The follower should accept the invitation, and download the Dexcom follow app. You
  can download Dexcom follow on the same phone as Dexcom main app, if you invited yourself as 
  follower.
* Make sure that the follower can see current Glucose, and graph. 

### Configure Blose

#### Add user

* Start Blose on the watch. 
* Select configure
* Select data source 
* Scroll down in the data source view, and click open on phone, alternatively open the shown
  url in a web browser on any device.
* Enter credentials into the shown form. For Dexcom: The credentials should be the same
  one as you use when you log in in Dexcom main app.
* Enter generated validation code into auth code field on the watch. No space is needed.
* Select region, if needed
* Click verify

#### Remaining configuration

All other configuration is optional. Configurations can be changed at any time, and the 
configuration dialog of Blose can be reached by starting the Blose app, 
and scroll down to configuration.

You can reach different sections of configuration by swiping sideways in the configuration dialog.

##### Sections

NOTE! Changing a configuration value can take up to 5 minutes before it gets applied to 
complications, and the tile. 

**Units**

* Select if mmol/L or mg/dL should be shown. 

**Glucose target**

* Define target range.
  Target range can affect visuals, in e.g the graph, but is also used when
  performing "in range" calculations. 

**Critical alarm**

* Specify if you want to be notified with a vibration when getting critically low

**Low alarm**

* Specify if you want to be notified with a vibration when getting low

**High alarm**

* Specify if you want to be notified with a vibration when getting high

**Actions**

* Defines what activity to start when a certain complication is tapped on. 
  I do e.g have the graph complication shown, and the glucose value shown.
  Taping on the graph starts the regular statistics view, but I have configured
  a glucose value tap to show the raw data view. 

**Graph**

* Show diff. This makes the graph complication show bars that gives you a visual indication
  of how fast the glucose is changing. A fast change is a high bar, a slow change is a low bar.
  Note that the bar just indicates how fast something is changing, not the direction of the change,
  e.g fast up, or fast down.
  Note! Can up to 5 minutes before it becomes visible in the graph view complication.

* Graph color schema. Affects the color of the bars in a graph complication.
  Note! Can up to 5 minutes before it becomes visible in the graph view complication.

* Max value. Affects the max value to show in the graph. A very high max value can make the 
  graph look flat if you often are in range. A very low max value will make the graph look
  as a flat line at the top of the view, since numbers that are higher than max value will 
  be shown at the top of the graph.
  Note! Can up to 5 minutes before it becomes visible in the graph view complication.

* Duration in graph. Max time frame to show in the graph complication.
  Note! Can up to 5 minutes before it becomes visible in the graph view complication.


## Complications

Blose can provide these complications. 

* Graph and glucose
  Type: Small image
  Description: A small image that shows graph and glucose. Can be used as a standalone complication.

* Graph
  Type: Small image
  Description: A large, 450 x 450 image that just shows the graph, and bars (if configured). 
  best used as a background complication. The top and bottom part of the image will always be transparent. 
  
* Glucose and trend
  Type: Ranged value, long text, short text. 
  Description: The watch face decides what to show. Long text will be glucose, trend and diff/delta. 
  Short text will be glucose and trend. Ranged value will be a value between 0 and 360, which
  represents the current glucose value. (I.e between 0-20 if mmol/L is used)

* Glucose timestamp
  Type: Short text
  Description: Shows how many minutes old the glucose value is. Best used as complication next
  to e.g. Glucose and trend

* Glucose only
  Type: Short text
  Description: The glucose value, without trend, diff/delta etc. 

* Glucose diff/delta
  Type: Short text 
  Description: How much the glucose increased/decreased compared to previous glucose reading. 

