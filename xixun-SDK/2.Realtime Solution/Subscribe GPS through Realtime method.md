subscribe GPS data from controller via realtime interface

Must use the specific Conn APK version

JSON command: 

##### 1. Subscribe gps

```json
{
    "type":"setSubGPS",
    "id":"643ca45c47cf7f0000b8504a",
    "openSub": true, //Enable
    "endpoint":"http://192.168.1.254:8080/progress/IpNotification", //uploading address
    "topic":"test/topic", //Subscribe -- default closed
    "interval":20, //second
    "mode": "http" //mqtt
    }
   // "endpoint":"a35u29xs1pm2ee-ats.iot.me-central-1.amazonaws.com",
```
##### 2. Get gps

```json
{
    "_type":"getSubGPS"
    }
```

##### 3. Cancel Subscribe

```
{
    "type":"setSubGPS",
    "id":"643ca45c47cf7f0000b8504a",
    "openSub": false, //Disable
    "endpoint":"http://192.168.1.254:8080/progress/IpNotification", 
    "topic":"test/topic", 
    "interval":20, //second
    "mode": "mqtt"
    }
```

