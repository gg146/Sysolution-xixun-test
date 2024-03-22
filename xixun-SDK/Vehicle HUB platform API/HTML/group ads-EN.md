>

#  group ads interface

Instructions

Catalogue 

1.1add group ads

1.2modify group ads

1.3(abandoned) send group ads

1.4delete group ads

1.5group ads list

1.6get group ads details

1.7Get information about the device that received the advertisement

1.8post ads

1.9cancel post

1.10update post time

1.11offline ads

1.12cancel terminating ads

1.13update offline time

1.14get information about device that received offline commands

1.15 download excel file contains all devices received ads

1.16excel download excel file contains all devices received offline ads command

1.17reset group ads

1.18export play log

1.19get play list

Add group ads

url:/v1/cms/groupAd/add

method:"post"

Need token or not: “Need”

Instructions：

 can not select if ungroup

Can always select the group no matter there is vehicle or not

Front end request json data, for example

Field  type  instructions  notes

name    string    description of ads  required    

group_id_list  string type’s array   vehicle group ID array  required

media_id string    material file id  required

duration  int  play duration   

time_span    object array  see example in below  optional

```
 {

  "time_span":[

​    {

​       "date_start":xxxx, // time stamp of start time

​      "date_end":xxxxx,// time stamp of end time

​      "day_start":xxxxx,// timestamp of the start time of the daily playback

​      "day_end":xxxxxx,//time stamp of the end time of the daily playback

​    }

  ]

}
```

//can be one element in the array at this present

Server side return data

```
{

  "data": {

​    "id": "5fa392a0a514083a14c7f88d"

  },

  "error_code": 9000,

  "msg": "create ads success"

}
```

Modify group ads

url:"/v1/cms/groupAd/:id/update"

method:put

Need token or not: need 

Instructions:

when status is Created, allow to modify

Front end request json data, example:

consistent with add interface 

Server side return data

```
{

  "error_code": 1003,

  "msg": "modify success"

}
```

(abandoned)send group ads

url:"/v1/cms/groupAd/id/send"

method:"put"

Need token or not:”Need”

Front end request json data, example:

None

Server side return data

```
{

  "error_code": 9001,

  "msg": "success"

}
```

Delete group ads

url:"/v1/cms/groupAd/:id/delete"

method:"delete"

Need token or note:”Need”

Instructions

when status is Offline allow delete

Front end request json data, example:

None

Server side return data

```
{

  "error_code": 9002,

  "msg": "delete success"

}
```

group ads list 

url:"/v1/cms/groupAd/list"

method:"get"

Need token or not:”Need”

Supported query parameters

Field  type  instructions

page int   page  default is 1

pageSize int   items in one page  default is 10

status    string    ads status  get all ads if not filled  Created  not post  WillPlace will post  WillOffline will offline Offline  offline

Server side return data

```
{

  "data": [

​    {

​      "id": "5fbcb8b9a514082dd4376475",

​      "name": "yyyyyyy",

​      "group_id_list": [

​        "5f9162b5a514082008e05966"

​      ], //group ads id

​      "duration": 10,

​      "media_type": 0,

​      "media_id": "5f8eaaeba514082394501354",

​      "date_created": "2020-11-24T15:39:37.215+08:00",

​      "status": "Offline", //ads status

​      "receive_device_number": 0, //device numbers received ads

​      "receive_device_list": [],//device id array that received ads

​      "is_place_trigger": false, //whether adopt delay post type, when the value is true, there is place_trigger_ts field in this data it is front end submitted time stamp 

​      "is_offline_trigger": false, //whether adopt delay offline type, when the value is true,offline_trigger_ts is the time stamp submitted by front end

​      "is_placed": true, //post or not

​      "is_offline": true, //offline or not

​      "place_device_count":10 ,//post device numbers

​      "offline_receive_device_list":[] ,

​      "offline_receive_number":0,

​      "time_span":[{

​        "date_start":xxxx,

​        "date_end":xxxxx,

​         "day_start":xxxx,

​        "day_end":xxx,

​      }]

​    },

​    {

​      "id": "5fbcb2d8a514082dd0b0892c",

​      "name": "wwwwww",

​      "group_id_list": [

​        "5f9162b5a514082008e05966"

​      ],

​       "duration": 10,

​      "media_type": 0,

​      "media_id": "5f8eaaeba514082394501354",

​      "date_created": "2020-11-24T15:14:32.566+08:00",

​      "status": "Place",

​      "receive_device_number": 2,

​      "receive_device_list": [

​        "mmm-nnn-999",

​        "s1-s2-s3"

​      ],

​      "is_place_trigger": false,

​      "is_offline_trigger": false,

​      "is_placed": true,

​      "is_offline": false,

​      "place_device_count":10 //post device numbers

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 2

}
```

Get group ads details

url:"/v1/cms/groupAd/:id/detail"

method:"get"

Need token or not:”Need”

Server side return data

```
{

  "data": {

​    "id": "5fbcbbd2a514081a7c9eb4c6",

​    "name": "asdsad",

​    "group_id_list": [

​      "5f9162b5a514082008e05966"

​    ],

​    "duration": 10,

​    "media_type": 0,

​    "media_id": "5f8eab01a514082394501355",

​    "date_created": "2020-11-24T15:52:50.51+08:00",

​    "status": "Place",

​    "place_device_count":10 ,//post device numbers

​    "group_detail": [

​      {

​        "id": "5f9162b5a514082008e05966",

​        "name": "1",

​        "type": 0,

​        "is_default": false,

​        "icon_url": "",

​        "date_created": "2020-10-22T18:45:09.82+08:00",

​        "online_taxi_number": 3,

​        "total_taxi_number": 3,

​        "taxi_list": [

​          {

​            "id": "mmm-nnn-999",

​            "card_id": "",

​            "name": "mmm-nnn-999",

​            "group_id": "5f9162b5a514082008e05966",

​            "driver_tel": "321312",

​            "taxi_photo_url": "",

​            "driver_name": "222",

​            "licence": "1111",

​            "imsi": "",

​            "iccid": "",

​            "online": true,

​            "card_detail": {

​              "online": false,

​              "width": 0,

​              "height": 0,

​              "brightness": 0,

​              "diskSize": 0,

​              "connVersion": "",

​              "connVersionCode": 0,

​              "playerVersion": "",

​              "playerVersionCode": 0,

​              "ledsetVersion": "",

​              "ledsetVersionCode": 0,

​              "updateVersion": "",

​              "updateVersionCode": 0,

​              "alias": "",

​              "netType": "",

​              "screenStatus": "",

​              "birSessin": "",

​              "currentProgramId": "",

​              "currentProgramName": "",

​              "volume": 0,

​              "locked": false,

​              "asu": 0,

​              "rssi": 0,

​              "temperature": 0,

​              "humidity": 0,

​              "transferred": false,

​              "sim": null,

​              "monitoringUrl": "",

​              "taxiAppVersion": "",

​              "taxiAppVersionCode": 0,

​              "basicAppVersion": "",

​              "basicAppVersionCode": 0,

​              "starterVersion": "",

​              "starterVersionCode": 0

​            },

​            "active_at": "0001-01-01T00:00:00Z"

​          },

​          {

​            "id": "s1-s2-s3",

​            "card_id": "s1-s2-s3",

​            "name": "s1-s2-s3",

​            "group_id": "5f9162b5a514082008e05966",

​            "driver_tel": "11111",

​            "taxi_photo_url": "",

​            "driver_name": "cxh",

​            "licence": "11111",

​            "imsi": "",

​            "iccid": "",

​            "online": true,

​            "card_detail": null,

​            "active_at": "0001-01-01T00:00:00Z"

​          },

​          {

​            "id": "qqq-www-eee",

​            "card_id": "qqq-www-eee",

​            "name": "qwggg",

​            "group_id": "5f9162b5a514082008e05966",

​            "driver_tel": "",

​            "taxi_photo_url": "",

​            "driver_name": "",

​            "licence": "",

​            "imsi": "",

​            "iccid": "",

​            "card_detail": null,

​            "active_at": "0001-01-01T00:00:00Z"

​          }

​        ]

​      }

​    ],

​    "receive_device_number": 2,

​    "receive_device_list": [

​      "mmm-nnn-999",

​       "s1-s2-s3"

​    ],

​     "offline_receive_device_list":[] ,

​      "offline_receive_number":0,

​    "is_place_trigger": false,

​    "is_offline_trigger": false,

​    "is_placed": true,

​    "is_offline": false,

​          "time_span":[{

​        "date_start":xxxx,

​        "date_end":xxxxx,

​        "day_start":xxxx,

​        "day_end":xxx,

​      }]

  },

  "error_code": 1001,

  "msg": "get data success"}
```

Get information about the device that received the advertisement

url:"/v1/cms/groupAd/:id/getReceiveStatus"

method:"get"

Need token or not: Need

Server return data

```
{

  "data": {

​    "receive_device_number": 0,

​    "receive_device_list": []

  },

  "error_code": 1001,

  "msg": "get data success"

}


```

 post ads

url:"/v1/cms/groupAd/:id/place"

method:put

Need token or not: Need

Instructions 

Can invoke this interface when status is Created

Request body data

Field  type  instructions  notes 

place_trigger_ts   int  time stamp of posting time  post immediately, then no need filled or value is zero

Returned json data

```
{

  "error_code": 9001,

  "msg": "post success"

}
```

Cancel post

url:"/v1/cms/groupAd/:id/cancelPlace"

method:put

Need token or not: Need

Instructions 

Invoke when status is WillPlace

Returned json data

```
{

  "error_code": 1003,

  "msg": "modify success"

}
```

Update time for posting ads

url:"/v1/cms/groupAd/:id/updatePlaceTime"

method:"put"

Need token or not: Need

Instructions

Can invoke when status is WillPlace

Request body data

Field  type instructions  notes

place_trigger_ts   int  time stamp of posting time, post immediately, then not filled or value is zero

Returned json data

```
{

  "error_code": 1003,

  "msg": "modify success"

}
```

 offline ads

url:"/v1/cms/groupAd/:id/offline"

method:put

Need token or not: Need

Instructions 

Can invoke this interface when status is place

Requested body data

Field  type  instructions  notes

offline_trigger_ts  int  time stamp of terminating time, offline immediately, then not filled or value is zero

Returned json data

```
{

  "error_code": 8001,

  "msg": "offline ads success"

}
```

Cancel offline ads

url:"/v1/cms/groupAd/:id/cancelOffline"

method:put

Need token or note: Need

Instructions 

Can invoke this interface when status is WillOflline

Returned json data

```
{

  "error_code": 1003,

  "msg": "modify success"

}
```

 update offline time

url:/v1/cms/groupAd/:id/updateOfflineTime

method:put

Need token or not: Need

Instructions 

Can invoke this interface when status is WillOffline

Request body data

Field  type  instructions notes

offline_trigger_ts  int  time stamp of offline time  offline immediately, no need filled or value is zero 

Returned json data

```
{

  "error_code": 1003,

  "msg": "modify success"

}
```

Get information about devices that received offline commands 

url:"/v1/cms/groupAd/:id/getOfflineReceiveStatus"

method:"get"

Need token or not: Need

Returned data, example:

```
{

  "data": {

​    "offline_receive_device_list": [

​      "mmm-nnn-999",

​      "s1-s2-s3"

​    ],

​    "offline_receive_number": 2

  },

  "error_code": 1001,

  "msg": "get data success"

}
```

download excel file contains all devices received ads

url:"/v1/cms/groupAd/:id/downloadReceivePlaceGroupAdReport"

method:"get"

Need token or not:Need. Can take token as query parameters and joint in the url ?auth_token=xxxxxx

Download success then return excel file

download excel file contains all devices received offline ads command

url:"/v1/cms/groupAd/:id/downloadReceiveOfflineAdReport"

method:"get"

Need token or not:Need. Can take token as query parameters and joint in the url ?auth_token=xxxxxx

Download success and return excel file 

Reset group 

url:"/v1/cms/groupAd/:id/resetGroup",

method:"put"

Need token or not:Need

Request body json data

Field  type  instructions

group_id_list  string type’s array   it’s group id array, need submit original group id and newly added group id together. If no new group added, then directly submit original group id array

Success and server return data

```
{

  "error_code": 9003,

   "msg":   "reset group success"

}
```

Export play log

url:"/v1/cms/playerLog/v1/cms/playerLog/getGroupAdPlayLog?auth_token=xxx"

method:"get"

Need token or not:Need. Can take token as query parameter auth_token=xxx and joint in the back of url 

Query parameters

Field  type instructions

id   string     the ads id 

beginTs  int  time stamp  var now_ts = new Date().getTime()

endTs    int  time stamp  var now_ts = new Date().getTime()

Operate success and return Excel file 

Get play log list 

url:"/v1/cms/playerLog/getGroupAdPlayLogList"

method:"get"

Need token or not: Need 

Supported query parameters

Field  type  instructions

page int   page number default is 1 if not filled

pageSize int   items in one page  default is 10 if not filled

id   string    the ads id 

beginTs  int  time stamp var now_ts = new Date().getTime()

endTs    int  time stamp var now_ts = new Date().getTime()

Server return data, example:

```
{

  "data": [

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:23:45 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14109

​    },

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:25:20 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14143

​    },

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:33:15 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14417

​    },

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:34:50 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14365

​    },

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:36:25 +0000 UTC",

​      "device_id": "e26-420-40713",

​       "duration": 14257

​    },

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:42:45 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14286

​    },

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:44:20 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14329

​    },

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:45:55 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14339

​    },

​    {

​      "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:52:15 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14293

​    },

​    {

​       "ad_id": "5ff400d0a514081fd8f1030f",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-01 03:53:50 +0000 UTC",

​      "device_id": "e26-420-40713",

​      "duration": 14632

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 32

}
```

