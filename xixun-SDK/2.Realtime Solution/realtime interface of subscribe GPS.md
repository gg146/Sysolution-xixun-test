subscribe GPS data from controller via realtime interface

Need to upgrade led controller CONN version 

JSON command: 

##### 1.subscribe gps

```json
{
    "type":"setSubGPS",
    "id":"643ca45c47cf7f0000b8504a",
    "openSub": true, //enable function
    "endpoint":"http://192.168.1.254:8080/progress/IpNotification", //upload address
    "topic":"test/topic", //subscribe -- default is closed
    "interval":20, //second
    "mode": "http" //mqtt
    }
   // "endpoint":"a35u29xs1pm2ee-ats.iot.me-central-1.amazonaws.com",
```
##### 2.Get gps

```json
{
    "_type":"getSubGPS"
    }
```

##### 3.Cancel subscribe

```
{
    "type":"setSubGPS",
    "id":"643ca45c47cf7f0000b8504a",
    "openSub": false, //disable function
    "endpoint":"http://192.168.1.254:8080/progress/IpNotification", 
    "topic":"test/topic", 
    "interval":20, //second
    "mode": "mqtt"
    }
```

