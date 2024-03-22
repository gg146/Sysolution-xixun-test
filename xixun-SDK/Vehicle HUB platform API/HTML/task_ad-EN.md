#  SanLe TaskAd api

Instructions Instructions

20200901 newly add four interfaces, use for adjust taskAd status 

keep original update interface no change, just for modify taskAd data

increase taskStatus type from 5 to 8, in below:

Created

WillPlace

StartPlace

PlaceFinished

WillOffline

StartOffline

OfflineFinished

Deleted

 catalogue 

1.1add ads data 

1.2modify ads data

1.3 post ads

1.4 offline ads

1.5 taskAd list

1.6 get post details

1.7 get offline details

1.8delete ads

1.9cancel post

1.10modify post date and time

1.11 cancel offline 

1.12 modify offline date and time

1.13 Get the device numbers of receiving specific ads post and offline commands 

add ads data

url:/v1/cms/taskAd/add

method:post

Need token or not: Need

Request body data

field  type  instructions  notes

name    string    ads name  required

media_type   int  media type  0 static image  1gif 2 video

media_id string    media file id   required

place_device_number  int  device number for posting ads  larger than 0, required. duration             int  play duration of the material  larger or equal to 1, required

response data 

```
{

  "error_code": 8002,

  "msg":"add success",

  "data":{

​    "id":"5cd177db5f627d23455f8cbd"

  }

}
```

Modify ads data 

url:/v1/cms/taskAd/:id/update

method:put

Need token or not: Need

Request data

Same interface like the one as above

Instructions：

When taskStatus is Created, can call this interface 

Response data 

```
{

  "error_code":1003,

  "msg":"modify success”

}
```

Post ads

url:/v1/cms/taskAd/:id/place

method:put

Need token or not: Need

Instructions

When taskStatus is Created can call this interface

Request parameters

field type   Instructions   notes

place_trigger_ts   int  time stamp  fill in 0 if not schedule one

Return data

```
{

  "error_code": 8000,

  "msg":    "post success"

}
```

Offline ads

url:/v1/cms/taskAd/:id/offline

method:put

Need token or not: Need

Instructions

When taskStatus is StartPlace 、PlaceFinished can invoke this interface 

When taskStatus is StartPlace, not support delay offline ads不支持延迟下线

Requests body parameters

field type   Instructions   notes

offline_trigger_ts  int  time stamp  fill in 0 if not schedule one

Response data

```
{

  "error_code": 8001,

  "msg": "offline ads success"

}
```

taskAd list

url:/v1/cms/taskAd/list

method:"get"

Need token or not: Need

Supported url query parameters（need supplement later）

field type   Instructions

page int  paging data

pageSize int  items obtained by one page

is_placed bool  query ads already posted, it can be false or empty character if don’t want to query this character string

is_offline bool  query ads already offline，it can be false or empty character if don’t want to query this character string

Return data

```
{paging data

  "data": [

​    {

​    "id": "5f91a1a0a5140826c4ee296d",     //id

​    "name": "sadas",              //name

​    "media_type": 0,              //media type

​    "media_id": "5f8eab01a514082394501355",  //media id

​    "duration": 10,              //play duration

​     "date_created": "2020-10-22T23:13:36.266+08:00", //create time

​    "place_device_number": 10,         //device number for post ads,filled in by users

​    "is_place_trigger": false,         // post ads by schedule or not    "place_trigger_ts":23423435434,     //post command trigger timestamp, whenis_place_trigger is true, should has value

​    "is_offline_trigger": false,        //offline ads by schedule or not

​    "offline_trigger_ts": 23423435434,    // offline command trigger timestamp, is_offline_trigger is true, has value 

​    "is_placed": true,             //post ads truly

​    "is_offline": false,            //offline ads truly

​    "place_received_device": ["mmm-nnn-999"], //devices groups received post command

​    "offline_received_device": [],       //devices groups received offline command

​    "task_status": "StartPlace",        // ads status

​    "place_receive_count": 0,         //numbers of device received post command

​    "offline_receive_count": 0         //numbers of device received offline command

  }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 2

}
```

Get post details

url:/v1/cms/taskAd/:id/getPlaceDetail

method:get

Need token or not: Need

Instructions：

When task_status is StartPlace、PlaceFinished、WillOffline、StartOffline、OfflineFinishedcan invoke

That is, when task_status is Created、WillPlace、Deleted ,not allow to invoke.

Also judge through is_placed is true

Return data is excel file

Excel contents as following

CARD_ID LICENCE(car license)

y30-444-666  xxx-xxxx-111

Get offline ads details

url:/v1/cms/taskAd/:id/getOfflineDetail

method:get

Need token or not: Need

Instructions：

When task_status is StartOffline、OfflineFinished can invoke

Can also judge through is_offline is true

Return data is excel

Excel content as following

CARD_ID LICENCE(car license )

y30-444-666  xxx-xxxx-111

Delete ads

url:"/v1/cms/taskAd/:id/delete"

method:"delete"

Need token or not: Need

Instructions

When task_status is Created、OfflineFinished can invoke

Return data

```
{

  "error_code":1004,

  "msg":"delete success"

}
```

Cancel post 

url:"/v1/cms/taskAd/:id/cancelPlace"

method:"put"

Need token or not: Need

Instructions：

When task_status is WillPlace, allow to invoke

Return data

```
{

  "error_code":1003,

  "msg":"modify success”

}
```

Modify post date and time

url:"/v1/cms/taskAd/:id/updatePlaceTime"

method:"put"

Need token or not: Need

Instructions：

When task_status is WillPlace allow invoke

Request data

```
{

  "place_trigger_ts":156788898676655 //time stamp //value is 0，means post immediately

}
```

Return data

```
{

  "error_code":1003,

  "msg":"modify success”

}
```

Cancel offline

url:"/v1/cms/taskAd/:id/cancelOffline"

method:"put"

Need token or not: Need

Instructions：

When task_status is WillOffline invoke this interface

Return data

```
{

  "error_code":1003,

  "msg":"modify success”

}
```

Modify offline date and time

url:"/v1/cms/taskAd/:id/updateOfflineTime"

method:"put"

Need token or not: Need

Instructions：

When task_status is WillOffline invoke this interface

Request data

```
{

  offline_trigger_ts:156788898676655 //timestamp //value is 0 means offline data immediately

}
```

Return data

```
{

  "error_code":1003,

  "msg":"modify success”

}
```

Get the device numbers of receiving specific ads post and offline commands

url:/v1/cms/taskAd/getReceiveDeviceCount

method:get

Need token or not: Need

Query parameters ()

field types  Instructions

id   string    the ads id, ,can not be empty

Back end return data

```
{

  "place_receive_count":10,

  "offline_receive_count":10

}
```

Export player log

url:"/v1/cms/playerLog/v1/cms/playerLog/getTaskAdPlayLog?auth_token=xxx"

method:"get"

Need token or not: Need. Can joint the token in the end of url in the form of query parameters auth_token=xxx

Query parameters

field type   Instructions

id   string    ads id

beginTs  int  timestamp var now_ts = new Date().getTime()

endTs    int  timestamp var now_ts = new Date().getTime()

Operation success and return Excel file

Get player log list 

url:"/v1/cms/playerLog/getTaskAdPlayLogLis"

method:"get"

Need token or not: Need

Supported query parameters

field type   Instructions

page int  page number default is1 if not fill in

pageSize int  items for one page  default is 10 if not fill in

id   string    the ads id

beginTs  int  timestamp var now_ts = new Date().getTime()

endTs    int  timestamp var now_ts = new Date().getTime()

Server return data, example:

```
{

  "data": [

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:57:25 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 4788

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:57:55 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:58:10 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:58:25 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:58:40 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:58:55 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:59:10 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:59:25 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:59:40 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    },

​    {

​      "ad_id": "60471bfba51408362c9a3a10",

​      "beginPlayLatitude": 0,

​      "beginPlayLongitude": 0,

​      "begin_play_time": "2021-03-09 06:59:55 +0000 UTC",

​      "device_id": "e06-a19-40004",

​      "duration": 5000

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 2593

}
```

