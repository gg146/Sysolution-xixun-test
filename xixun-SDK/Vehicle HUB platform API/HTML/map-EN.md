# Related interfaces of the map page in web portal 

instructions 

1.3 contains all fields of 1.2

1.2 existed for compatible with older version.

catalogue

1.1 get single device gps tracking, original getCardTrack

1.2Get the last GPS location of all devices under the current account at one time, original getAllCardLocations

1,3Get all controllers information under the current account, enhanced version of original getAllCardLocation

1.4Monitor all controllers online and offline under the current account in the real time, original watchOnline

1.5Feedback controller location information in the real time, original WatchCardLocation

1.1Get signal device gps tracking 

url:"/v1/cms/map/getCardTrack"

method:websocket  persistent connection 

Need token or not: need token and joint token in the end of url as query parameters, auth_token=xxxxxx

Will server actively disconnect after sending all data? Yes, it will. 

Device needs to send following data after connected

```
{

  "card_id":"yyy-888-999",

"begin_at":1567889999555,  //the time stamp of the start time of the query 

  "end_at":1567889999555   //the time stamp of the end time of the query

}
```

Server return data field at one time

```
{  

  "card_id":"yyy-888-999",

  "location":{

​     "timestamp":1567889999555,   //time stamp

​    "lat":0.0,

​    "lng":0.0,          // Latitude and longitude 

​    "speed":  0,            

​    "bearing":0,

​    "distance":0,

  }

}
```

1.2Get the last gps location information of all devices under the current account

url:"/v1/cms/map/getAllDevicesLocation"

method:webSocket persistent connection 

Need token or not: need token and joint token in the end of url as query parameters, auth_token=xxxxxx

Will server actively disconnect after sending all data? Yes, it will. 

Server return data at one time

```
{  

  "card_id":"yyy-888-999",

  "location":{

​     "timestamp":1567889999555,   //time stamp

​    "lat":0.0,

​    "lng":0.0,          //latitude and longitude

​    "speed":  0,            

​    "bearing":0,

​    "distance":0,

  }

}
```

1.3 Get all controllers information under the current account(this interface contains all filed that in 1.2, recommend to use)

url:"/v1/cms/map/getAllCardInfo"

method:webSocket persistent connection

Need token or not: need token and joint token in the end of url as query parameters, auth_token=xxxxxx

Will server actively disconnect after sending all data? Yes, it will. 

Server return data at one time

```
{

  "id":"yyy-333-999",

  "card_id":"yyy-333-999",

  "name":"cxh_test",

  "group_id":null,

  "driver_tel":110,

  "taxi_photo_url":"11111",

  "driver_name":"cxh",

  "licence":"1111111",

  "imsi":"",

  "iccid":"",

  "online":true,

  "location":{

​    "timestamp":1567889999555,  

​    "lat":0.0,

​    "lng":0.0,           

​    "speed":  0,            

​    "bearing":0,

​    "distance":0,

  }

}
```

1.4Monitor all controllers online and offline under the current account in the real time

url:"/v1/cms/map/watchOnline"

method:webSocket persistent connection

Need token or not: need token and joint token in the end of url as query parameters, auth_token=xxxxxx

Will server actively disconnect after sending all data? No, because devices will get online and offline in the real time, so the server will not disconnect 

Server return data at one time

```
{

  "card_id":"yyy-333-1111",

  online:true

}
```

1.5Feedback controller location information in the real time

url:"/v1/cms/map/watchLocation",

method:webSocket persistent connection

Need token or not: need token and joint token in the end of url as query parameters, auth_token=xxxxxx

Will server actively disconnect after sending all data? No, because devices will get online and offline in the real time, so the server will not disconnect 

Server return data at one time

```
{  

  "card_id":"yyy-888-999",

  "location":{

​     "timestamp":1567889999555,   //time stamp

​    "lat":0.0,

​    "lng":0.0,          //latitude and longitude

​    "speed":  0,            

​    "bearing":0,

​    "distance":0,

  }

}
```

