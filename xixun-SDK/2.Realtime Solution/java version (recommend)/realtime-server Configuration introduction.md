# realtime-server setup

## 1.run realtime service

enter the control in the current page after finishing download

![](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/1.png)
![](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/2.png)

then input java-jar netty-wss.jar to run up service, see the screenshot of successful run up:

![image-20230721133702287](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/3.png)

## 2.communication setup for led controller

the communication port is 10010, run LEDOK express and setup 

![image-20230912143629803](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/4.png)

see screenshot of successful connection 

![image-20230721134136221](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/5.png)

## 3.start to test API

can start to test API according to our API document after setup communication success

![image-20230912143820899](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/6.png)

![image-20230912143852031](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/7.png)

take turn on/off led screen for example, open postman software, send type is Post, data format is JSON , path is IP+port8084+command+controller serial ID  

![image-20230721135252465](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/8.png)



Must remove the explanation when sending command or will create error 

![image-20230721135422524](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/9.png)

this means send success



can modify port in yml 

![image-20230721154733583](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/10.png)

![image-20230912144816038](https://github.com/gg146/Sysolution-xixun-test/blob/master/xixun-SDK/2.Realtime%20Solution/java%20version%20(recommend)/image/11.png)

need to restart service after modify port, then use the new port to send command. 
