#  region ads modem interfaces

 instructions 

catalogue 

 add a region ad

url:"/v1/cms/regionAd/add"

method::"post"

Need token or not: need

Request parameters

Field  type  instructions  notes

name    string    description of ads  

media_id string     material address

group_id_list  string  type’s array  group id array 

region_id_list string  type’s array  region id array     

time_span    object array, see example in below:

```
{

  time_span:[

​    {

​      "date_start":1596076369985 ,      //time stamp of start date

​      “date_end:1596076369985,        //time stamp of end date

​      "day_start":0,              //The starting hour of each day in the above time period

​      "day_end":82800            //The ending hour of each day in the above time period

​    }

  ]

}
```

 response data

```
{

  "error_code":1002,

  "msg":"add success”

}
```

Delete a region ads

url:"/v1/cms/regionAd/delete"

method:"delete"

Need token or not: Need

Response data

```
{

  "error_code":1004,

  "msg":"add success”

}
```

Update an ad

url:"/v1/cms/regionAd/:id/update"

method:"put"

Need token or not: Need

Request data

It is the same request data as add a region ad

Response data

```
{

  "error_code":1003,

  "msg":"delete data”

}
```

Get details

url:"/v1/cms/regionAd/:id/detail"

method:"get"

Need token or not: Need

Return data

```
{

  "data": {

​    "id": "5f2778f9a5140820a4c11a41",

​    "date_created": "2020-08-01T13:37:19.822+08:00",

​    "ad_desc": "222222",

​    "time_span": [

​      {

​        "date_start": 1584720000000,

​        "date_end": 1586534400000,

​        "day_start": 0,

​        "day_end": 82800

​      }

​    ],

​    "regions": [

​      {

​        "id": "5f250d6ca51408162c4075d1",

​        "date_created": "2020-08-01T14:36:28.102+08:00",

​        "name": "789",

​        "lat": "120.11111",

​        "lng": "89.22222",

​        "currency": 1,

​        "radius": 8888,

​        "price": 1222,

​        "is_foreign": false,

​        "allow_deleted": 0

​      }

​    ],

​    "groups": [

​      {

​        "id": "5f23c018a51408243c1d05e6",

​        "name": "test1111",

​        "type": 0,

​        "occupied": true,

​        "is_default": false,

​        "icon_url": "",

​        "date_created": "2020-07-31T14:54:16.208+08:00",

​        "online_taxi": 0,

​        "offline_taxi_number": 0

​      }

​    ],

​    "media_url": "01DSM4DPDSJN44KRZ409Z889GY",

​    "material_type": 0,

​    "is_published": false

  },

  "error_code": 1001,

  "msg": "get data success"

}
```

Get list 

url:"/v1/cms/regionAd/list"

method:"get"

Need token or not: Need

Supported query parameters

Filed  type  instructions

page int default is 1 if not filled

pageSize int   default is 10 if not filled

Response data

```
{

  "data": {

​    "id": "5ff2c156a514080a08d2d77d",

​    "date_created": "2021-01-04T15:18:46.452+08:00",

​    "name": "xxxx",

​    "time_span": [

​      {

​        "date_start": 1596076369985,

​        "date_end": 1596076369985,

​        "day_start": 0,

​        "day_end": 82800

​      }

​    ],

​    "group_id_list": [

​      "5f9162b5a514082008e05966"

​    ],

​    "region_id_list": [

​      "5ff2bc36a5140838181cead0"

​    ],

​    "region_detail": [

​      {

​        "id": "5ff2bc36a5140838181cead0",

​        "date_created": "2021-01-04T14:56:54.463+08:00",

​        "name": "xxxx",

​        "lat": "31.111111",

​        "lng": "123.1111111",

​        "currency": 0,

​        "radius": 10000,

​        "tag_list": null,

​        "price": 0,

​        "is_foreign": false,

​        "allow_deleted": 0

​      }

​    ],

​    "group_detail": [

​      {

​        "id": "5f9162b5a514082008e05966",

​        "name": "1"

​      }

​    ],

​    "medial_id": "5f50ac11a51408156c3212d9",

​    "media_type": 0,

​    "is_published": false

  },

  "error_code": 1001,

  "msg": "get data success"

}

Post fixed point ads

url:"/v1/cms/regionAd/:id/place"

method:"post"

Need token or not: Need

Operate success and return data



{

  "error_code": 7008,

​    "msg":     "place success"

}
```

Export the player log of fixed point ads

url:"/v1/cms/playerLog/getRecentRegionAdPlayLog?auth_token=xxx"

method:"get"

Need token or not: Need. Can joint token in the end of url in the form of query parameters 169.254.255.254

Query parameters

Filed  type  instructions

id   string     the ad id

beginTs  int  time stamp var now_ts = new Date().getTime()

endTs    int  time stamp var now_ts = new Date().getTime()

Operate success and return Excel file

Get play log list

url:"/v1/cms/playerLog/getRecentRegionAdPlayLogList"

method:"get"

Need token or not: need

Supported query parameters

Field type instructions

page int  page number  default is 1 if not filled

pageSize int  items in one page default is 10 if not filled

id   string    the ad’s id

beginTs  int  time stamp var now_ts = new Date().getTime()

endTs    int  time stamp var now_ts = new Date().getTime()

Example: server return data

```
{

  "data": [

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771547,

​      "beginPlayLongitude": 121.32795699,

​      "begin_play_time": "2021-03-09 06:47:19 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771329,

​      "beginPlayLongitude": 121.32796292,

​      "begin_play_time": "2021-03-09 06:47:29 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771292,

​      "beginPlayLongitude": 121.32796201,

​      "begin_play_time": "2021-03-09 06:47:59 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771209,

​      "beginPlayLongitude": 121.32795824,

​      "begin_play_time": "2021-03-09 06:48:29 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771139,

​      "beginPlayLongitude": 121.32795398,

​      "begin_play_time": "2021-03-09 06:48:59 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771094,

​      "beginPlayLongitude": 121.32795314,

​      "begin_play_time": "2021-03-09 06:49:30 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771065,

​      "beginPlayLongitude": 121.32795202,

​      "begin_play_time": "2021-03-09 06:50:00 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771045,

​      "beginPlayLongitude": 121.32795077,

​      "begin_play_time": "2021-03-09 06:50:30 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23771017,

​      "beginPlayLongitude": 121.32794834,

​      "begin_play_time": "2021-03-09 06:51:00 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​      "region_name": "xixun"

​    },

​    {

​      "ad_id": "6047125da51408362c9a39ec",

​      "ad_name": "xixun-004",

​      "beginPlayLatitude": 31.23770952,

​      "beginPlayLongitude": 121.32794696,

​      "begin_play_time": "2021-03-09 06:51:30 +0000 UTC",

​      "device_id": "e26-420-40721",

​      "duration": 10000,

​      "region_id": "5ff91d96a514081f30fed8ff",

​       "region_name": "xixun"

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 2208

}
```

