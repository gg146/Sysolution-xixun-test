#  vehicle information interface

Instructions

 catalogue

 vehicle list 

update vehicle information

get vehicle detailed information

switch vehicle accounts in bulk 

query vehicle total numbers and online numbers under current account

set vehicle background

download offline vehicle report

Download the Excel template for vehicle information

excel Upload Excel for modify vehicle information in bulk

get vehicle ads information 

delete vehicle

delete vehicle in bulk

change vehicle group

vehicle list

url:/v1/cms/taxi/list

method:get

Need token or not: Need

Supported query parameters

field  type  instructions 

page int  default is page 1 if not filled

pageSize int  default is 10 if not filled

name    string    not query if not filled (support fuzzy enquiry )

driver_tel string    not query if not filled (support fuzzy enquiry )

driver_name  string    not query if not filled (support fuzzy enquiry )

id   string    not query if not filled (support fuzzy enquiry )

licence   string    not query if not filled (support fuzzy enquiry )

group_id string    query specific group data, query all vehicle data if not filled, if want to query ungrouped data, need fill in null character string

sortTaxiBy    string     

Response 

```
{

  "data": [

​    {

​      "id":"y39-777-999",

​      "card_id": "y39-777-999",

​      "name": "1111111",

​      "driver_tel": "",

​      "taxi_photo_url": "http:xxxxx/taxi.jpg",

​      "driver_name": "taxi",

​      "licence": "666-8888-9999",

​      "imsi": "abc",

​      "iccid": "qqqqqqqq"

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 1

}
```

update vehicle information

url:"/v1/cms/taxi/:id/update",

method:put

Need token or not: Need

 request parameters

field type  instructions 

name    string    not required, required

driver_tel string    not required, telephone number

driver_name  string    not required,driver name

 licence  string    not required, vehicle license 

response

```
{

 "error_code":1003,

 "msg":"updated success" 

}
```

get vehicle detailed information

url :/v1/cms/taxi/:id/detail

method:get

Need token or not：need 

Response data

```
{

  "data": [

​    {

​      "id":"y39-777-999",

​      "card_id": "y39-777-999",

​      "name": "1111111",

​      "driver_tel": "",

​      "taxi_photo_url": "http:xxxxx/taxi.jpg",

​      "driver_name": "taxi",

​      "group_name":"xxxxx",

​      "licence": "666-8888-9999",

​      "imsi": "abc",

​      "iccid": "qqqqqqqq",

​      "online":true,

​      "card_detail":{

​          "alias" : "0101",

​          "asu" : 8,

​          "basicAppVersion" : "1.0",

​          "basicAppVersionCode" : 1,

​          "brightness" : 64,

​          "connVersion" : "10.0.9T",

​          "connVersionCode" : 109,

​          "currentProgramId" : null,

​          "currentProgramName" : null,

​          "diskSize" : 0,

​          "height" : 96,

​          "humidity" : 0,

​          "ip" : "::ffff:192.168.8.1800101",

​          "lastOnline" : ISODate("2019-09-01T02:20:57.435Z"),

​          "ledsetVersion" : "5.1.9.3",

​          "ledsetVersionCode" : 550,

​          "locked" : false,

​          "netType" : "ETH",

​          "playerVersion" : "10.3.2",

​          "playerVersionCode" : 332,

​          "rssi" : -200,

​          "tag" : "0101"

​      }

​    }

  ],

  "error_code": 1001,

  "msg": "get data success",

  "totalCount": 1

}
```

switch vehicle accounts in bulk 

url:"/switchTaxiAccount",

method:"post"

Need token or not: need

Request body data instructions

field  type  instructions  notes

card_list string type array  there is one item is device id, such as y30-120-01093, can not be empty array

token    string    can not be empty, must be the corresponding value of account_id_token field in the downloaded token. Can not be empty

url  string    target server address   can be empty 

server return data

```
{

  "error_code":3000,

  "msg":"Generate Switch Account cmd Succeed"

}
```

query vehicle total numbers and online numbers under current account

url:"/v1/cms/taxi/getOnlineAndTotalCount"

method:"get"

Need token or not:Need

server return data

```
{

  "data": {

​    "online": 0,

​    "total": 4

  },

  "error_code": 1001,

  "msg": "get data success"

}
```

 set vehicle background

url :"/v1/cms/taxi/setTaxiBackGround",

method:"post"

Need token or not:Need

Request body data

field  type  instructions  notes

card_list string type data  vehicle id array  can not be empty array, required

media_id string    media file id   can not be empty, must be the legal id

background_type  Enumeration of string types   command type  brake  route   turn_left turn_right vacant hired no_service booked 

//example 

```
{

  "card_list":["y60-620-40358"],

  "media_id":"5f477a30a51408189cb64d0b",

  "background_type":"brake"

}
```

success server return data

```
{

  "error_code": 3002,

  "msg": "send data success"

}
```

 download offline report

url:"/v1/cms/user/downLoadIOfflineReportFile"

method:"get"

Need token or not: “Need”, suggest to joint the token in the end of query parameter auth_token=xxxxxx

Supported query parameters

field  type  instructions

group_id string    query specific group data, query all vehicle data if not filled, if want to query ungrouped data, need fill in null character string

Download the Excel template for vehicle information

url:"/downloadTaxiInfoTemplate"

methed:"get"

Need token or not: No need

Supported query parameters

field  type  instructions 

lng  string    zh or en

Upload Excel for modify vehicle information in bulk

url:"/v1/cms/taxi/batchUpdateTaxiInfoFromExcel"

mehtod:"post"

Need token or not: Need

Adopt upload forms, form ‘s name value is file, see screenshot in below:

 get vehicle ads information 

url:/v1/cms/taxi/getTaxiAdList?auth_token=xxxxx

method:"websocket"

Need token or not: “Need”, can joint token in the end of url, that is auth_token=xxx

Close server actively or not: “yes”

Server return data for one time, example: 

```
{  

  "isSuccess":true, //when it is false, need to show errMsg

  "errMsg":"ok",

  "card_id":"e20-111-222",

   ad_list:[

​    {

​      "id":"qqqqqq",

​      "ad_type":"" , //ads by grouping:group_ad ads by quantity：task_ad ads by regional：region_ad 

​      "name":"xxxxx",

​      "media_url":"xxxxxxx",

​    },

​    {

​      "id":"qqqqqq",

​      "ad_type":"" ,

​      "name":"xxxxx",

​      "media_url":"xxxxxxx",

​    }

  ],

  "current_ad_list":[

​    {

​      "id":"xxxxxx",

​      "ad_type":"region_ad",

​      "name":"xxxxx",

​      "media_url":"xxxxxxx",

​    }  

  ]

}
```

 delete vehicle

url:"/v1/cms/taxi/:id/delete"

method:"delete",

Need token or not:”Need”

Delete success return 200

Delete vehicle in bulk 

url:"/v1/cms/taxi/batchDeleteTaxi"

method:"post"

Need token or not:”Need”

Request body data

```
{

  "card_list":["e30-111-222","e35-222-000"]

}
```

Delete success return 200

 sending query command to device

url :"/v1/cms/taxi/sendQueryCommandForTaxiApp",

method:"post"

Need token or not:”Need”

Supported query commands：

Query ads order

//web->server

```
{

  "card_id":"xxxx",

  "_type":"get_advertise_order"

}
```

//server->web

```
{

  "data": {

​    "card_id": "e26-420-40721",

​    "group_ad_list": [

​      {

​        "id": "60471bfba51408362c9a3a10",

​        "name": "004",

​        "media_id": "5ffd572fa514081698f23a21",

​        "media_type": 0

​      }

​    ],

​    "group_ad_id_list": [    //for debug, no need show up

​      "60471bfba51408362c9a3a10"

​    ]

  },

  "error_code": 1001,

  "msg": "get data success"

}


```

Query ads content

// web ->server

```
{

  "card_id":"xxxx",

  "_type":"get_ad_list"

}
```

// server->web

```
{

  "data": {

​    "card_id": "e26-420-40721",

​    "ad_list": [

​      {

​        "id": "60471bfba51408362c9a3a10",

​        "ad_type": "task_ad",

​        "name": "004",

​        "media_id": "5ffd572fa514081698f23a21",

​        "media_type": 0,

​        "download_progress":"10"

​      }

​    ],

​    "current_play_list": [

​      {

​        "id": "60471bfba51408362c9a3a10",

​        "ad_type": "task_ad",

​        "name": "004",

​        "media_id": "5ffd572fa514081698f23a21",

​        "media_type": 0,

​         "download_progress":"10"

​      }

​    ]

  },

  "error_code": 1001,

  "msg": "get data success"

}
```

Modify vehicle group

url:"/v1/cms/taxi/modifyGroup"

method:"put"

Need token or not: Need

Json field in the request body

```
{

  "card_id_list":["y30-111-222","y60-222-333"], //card serial id that need to do operate

  "target_group_id":"xxxxx" //target group, if ungroup, need fill in “null” character string

}
```

Return data from server

```
{

  "error_code":1003,

  "msg":"update success"

}
```

Force to offline group ads

url:"/v1/cms/taxi/offlineGroupAdForDevice"

method:"post"

Need token or not:Need

Json field in request body

```
{

  "group_ad_id":"60643588a51408127c45aa3d",

  "device_list":["1_taxi"]

}
```

Operate success return data

```
{

  "error_code": 9002,

  "msg": "delete success"

}
```

Get simple list of group ads (only contains the necessary fields) url:"/v1/cms/groupAd/getGroupAdSimpleList"

method:"get"

Need token or not:Need

Supported query parameters

field type  instructions

page int  current page, default is 1 if not filled

pageSize int  items in one page, default is 10 if not filled 

Return result data

```
{

  "data": [

​    {

​      "id": "606d5113a514086fcca7fec5",

​      "name": "1",

​      "media_type": 0,

​      "media_id": "5f8eaaeba514082394501354",

​      "date_created": "2021-04-07T14:28:35.249+08:00"

​    },

​    {

​      "id": "606d4e4da514086fcca7fec4",

​      "name": "123",

​      "media_type": 0,

​      "media_id": "5ff274bba51408229433cc26",

​      "date_created": "2021-04-07T14:16:45.624+08:00"

​    },

​    {

​      "id": "606686c2a5140827d0379a8b",

​      "name": "21",

​      "media_type": 0,

​      "media_id": "5ff274bba51408229433cc26",

​      "date_created": "2021-04-02T10:51:46.43+08:00"

​    },

​    {

​      "id": "606577a9a5140805681a8a6b",

​      "name": "saddsad",

​      "media_type": 0,

​      "media_id": "5f8eaaeba514082394501354",

​      "date_created": "2021-04-01T15:35:05.572+08:00"

​    },

​    {

​      "id": "60657775a5140805681a8a6a",

​      "name": "asdsad",

​      "media_type": 0,

​      "media_id": "5f8eab01a514082394501355",

​      "date_created": "2021-04-01T15:34:13.658+08:00"

​    },

​    {

​      "id": "60643588a51408127c45aa3d",

​      "name": "qweqwe",

​      "media_type": 0,

​      "media_id": "5f8eab01a514082394501355",

​      "date_created": "2021-03-31T16:40:40.161+08:00"

​    },

​    {

​      "id": "6064354fa51408127c45aa3b",

​      "name": "qweewrdfsgdf",

​      "media_type": 0,

​      "media_id": "5f8eab01a514082394501355",

​      "date_created": "2021-03-31T16:39:43.476+08:00"

​    },

​    {

​      "id": "6064300aa51408127c45aa3a",

​      "name": "zxczxczxc",

​      "media_type": 0,

​      "media_id": "5ff274bba51408229433cc26",

​      "date_created": "2021-03-31T16:17:14.641+08:00"

​    },

​    {

​      "id": "606423dca51408127c45aa37",

​      "name": "cxvcxvcxv",

​      "media_type": 0,

​      "media_id": "5f8eab01a514082394501355",

​      "date_created": "2021-03-31T15:25:16.436+08:00"

​    },

​    {

​      "id": "606422e3a51408127c45aa36",

​      "name": "asdasdd",

​      "media_type": 0,

​      "media_id": "5f8eab01a514082394501355",

​      "date_created": "2021-03-31T15:21:07.862+08:00"

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 31

}
```

