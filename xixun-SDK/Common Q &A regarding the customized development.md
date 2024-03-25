# Common Q &A regarding the customized development

##### How to choose the solutions from the SDK？

1. Solution 1 is develop own APP, directly install into sysolution controller, so that your own platform can control the APP to publish content. Of course, need to uninstall controller's xixunplayer app. 
2. Solution 2 is the Sysolution Realtime Server, so that customer can build up the realtime server in the LINUX or Windows in LAN or WAN freely, just need to docking the functions API then can use it. It will cost less development time, for simple functions, can be done within one week time. 
3. Solution 3 is develop websocket server and connect to the sysolution controller. All the API are the same of AIPS2.0  platform, which means all the functions supported by AIPS2.0 can be realized in websocket server. But this will cost long development time and more works, belong to deeply customized development. 
4. Solution 4 is LAN solution, customer can push the content through TCP type and call Sysolution controller Interface by HTTP type. 

##### what numbers stand for in xixunplayer? (xixunplayer version below 1600 will have numbers)

  1: means not receive any program task ; 2: program task play finish; 3: there is no program task or the schedule time not start; 4: delete program task ; 5: processing the program task 

##### send command to controller and return Error: invalid command

  it means the command is error, please check if the command has been sent correctly. If the solution is different, then the API also different, can not mix. 

##### no display on screen after sending program task, no play

please check the json, url can download material links success, if success, please check size and totalsize values are correct or not. 

##### Why it is black screen after sending program task ?

Normally the black screen caused by material resolution, we recommend the image and video resolution 320-720p, no more than 1280x720. 

##### How to edit format for image and video. 

The video only supports 3GP and MP4. Please prioritize using Divx, Xvid, AVC/H.264 for MP4 encoding. Other encoding formats may cause playback errors! Please convert the video size to the size you want to play, or use a commonly used video ratio (320p~720p). If the video width is greater than 1280 or the height is greater than 1080, it will cause playback errors! The image only supports RGB color mode. CMYK mode will cause black screen playback. If it cannot be played, please convert the image color mode to RGB mode (professional image processing software such as Photoshop is required)

##### Why the HTML webpage I designed can not work, just show black screen?

There are some reasons for this issue, but the mostly is the js code compatible reason. 

1. First, check the Android version of the control card. If the version is low, the built-in browser will be low, and the rendering effect will be poor
2. please contact us to test it with other high Android versions

##### How to adjust json play in loop ?

each sources stand for a material. if want the images play in loop, then make sure to use the same numbers of resources for numbers of materials in loop playback. 

##### why always show laptop or computer actively reject when connecting network adb?

go to ledok express software, terminal control--> advanced settings, password is 888

then right click to open hide menu, turn on ADB debug function switch for several times then will be ok. 

##### Why my own APK can not auto run up ?

Sysolution controller default apk run up by broadcast way, so for your own apk, please add auto boot up codes. 

##### How to build up realtime server to test?

please refer to the tutorial:

[https://gitee.com/sysolution/xixun-test/blob/master/2.%E6%96%B9%E6%A1%88%E4%BA%8C%EF%BC%9Arealtime%E5%BC%80%E5%8F%91%E6%96%B9%E6%A1%88/java%E7%89%88%E6%9C%AC%E6%9C%8D%E5%8A%A1(%E6%8E%A8%E8%8D%90)/realtime-server%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E.md

##### How to get Sysolution led controller GPS Latitude and Longitude for my own APK?

there are some gps using serial port modem, so that can not use android API to get the gps data. the solution is directly monitor this broadcast and get the gps data, so when the led controller has GPS data will send a broadcast

```
Third party APP get GPS data from xixun controller

Method:

Monitor broadcast character string："com.xixun.joey.gpsinfo"，
Get the character string through the received Extra data：
"latitude" get latitude，double type
"longitude" get longitude，double type
Example code：
Register monitor broadcast：
IntentFilter filter = new IntentFilter();
filter.addAction("com.xixun.joey.gpsinfo"); 
context.registerReceiver(listener, filter);
Receiving data and process：
public void onReceive(Context arg0, Intent arg1) {
	if(arg1.getAction().equals("com.xixun.joey.gpsinfo ")){
		double lat = arg1.getDoubleExtra("latitude ", 0);
		double lng = arg1.getDoubleExtra("longitude ", 0);
	}else;
```

##### Why there is time out issue?

Mostly reason is Network delay caused the time out. 

##### How to judge the controller is online or not, can not find this API?

Normally we can query controller basic information command, if command go through success, means it is online. 

##### How to set the id value in API?

ID value is random one, no need to get in specific. 

##### How to choose realtime server for JAVA or NODE version?

recommend to choose java version. we will not update node version, because if too many led controllers access to node version, will cause server crash and not stable. 

##### How to judge the bugs has matter with the customized development platform?

You can bind the led controller to the AIPS2.0 platform and check the same function, if the AIPS2.0 platform works fine, means it is the customized platform has problem, please check the codes. 

##### Some clients find that the led controllers can not work with existed customized development platform?

Because led controller android version may not different, which may cause the compatible issue, please keep to use the same android version of the led controller.  