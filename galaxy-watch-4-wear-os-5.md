# Galaxy Watch 4

Galaxy Watch 4 did initially come with Wear OS 3, but can be upgraded to Wear OS 5. 

## Wear OS 3 and 4

Wear OS 3 and 4 did allow applications to have watch faces in them, so Blose had a watch face included. Wear OS 5 removed watch face support from applications, and watch faces must be downloaded separately. 

## Wear OS 5

Applications that want to perform work frequently, e.g once every 5 minutes _must_ ask for scheduling permissions. An application that doesn't have the permission to schedule will get delayed executions, 
and some work can be postponed for a very long time. Blose does for that reason require scheduling permission approval. Wear OS 5 did also remove support for watch faces in applications. 

## Known quirks in Wear OS 5 on Galaxy watch 4

Opening the permissions dialog can take a very long time, and a spinner is shown while it's loading. Try to keep the screen on while it's loading. 
The permission dialog is a part of the OS, and is triggered by Blose. Any bugs and quirks in the permission dialog are caused by Google, not Blose. 

The permission dialog, when loaded will show apps that you can give scheduling permission. Blose will be one of those apps. The toggle might initially be shown as 
allowed, but the text says denied. Tap on Blose, tap on the toggle so it looks like it's turned off, and then tap it again, so it looks like it's turned on. 
*Don't* swipe back in the permission dialog, since the value then will be reset again. Do instead click on the top right physical button on the watch, so that you get
back to your current watch face, and then start Blose again. Blose should now detect that it has scheduling permissions, and you should be able to configure the app. 


