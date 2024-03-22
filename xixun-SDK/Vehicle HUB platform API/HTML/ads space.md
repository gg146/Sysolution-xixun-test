# Ads container modem interface ( that is ads space )

catalogue

Create ads space

url:/v1/cms/adContainer/add

method:post

Need token or not: Need

Request data

field  type  instructions note

name    string    required, ads space name     

play_duration int  required, ads display duration in this ads space 

pause_while_move boolean  ads stop when vehicle moving     

price     int  cost of display ads one time, unit : minute 

currency int  cost type, 0 means RMB, 1 means USD, must be 0 or 1, if not any of them, then will be error

taxi_group_list     string type array  array length at least be 1,and each item in the array must be a legal ID string  

floor_count   int  check the floor numbers of this ads space, which is ads unit, maximum is 10 floors

Response data 

```
{

  "error_code": 1002,

  "msg":"add success"  

}
```

Delete ads space

url :"/v1/cms/adContainer/:id/delete"

method:"delete"

Need token or not: Need

Response data 

```
{

  "error_code":1004,

  "msg":"delete data success"

}
```

Get ads space data list page 

url:/v1/cms/adContainer/list

method:get

Need token or not: Need

Supported query parameters, all query parameters were filled according to the requests

field  type  instructions

page int  default is 1 if not filled

pageSize int  default is 10 if not filled

duration  int  will not Carry in query criteria if not filled 

occupied_begin    utc time(If it is difficult to do, it can be changed to a timestamp)  

occupied_at  utc time(If it is difficult to do, it can be changed to a timestamp) This field needs to be paired with the above field. Once this query is brought, it is not within this time period

Response data

```
{

​    "error_code": 1000,

​    "msg":     "get data success",

​    "totalCount": 1,

​    "data":    [{

​      "id" : "5f0eba65a5140828b87b6db2",

​      "name" : "adConainer-test",

​      "play_duration" :10,

​      "pause_while_move" : false,

​      "is_default" : false,

​      "price" : 10,

​      "currency" : 0,

​      "taxi_group_list" : [ "5f0eb6b1a5140828b87b6db1"],

​      "floor_count" : 1,

  }]

}
```

Get details page

url:/v1/cms/adContainer/:id/detail

method:get

Need token or not: Need

Response data

```
{

  "data": {

​    "id": "5f23c031a51408243c1d05e7",

​    "name": "test",

​    "play_duration": 10,

​    "pause_while_move": false,

​    "is_default": false,

​    "price": 10,

​    "currency": 0,

​    "floor_count": 2,

​    "floors": [

​      {

​        "id": "5f23c031a51408243c1d05e8",

​        "position_ad_list": null

​      },

​      {

​        "id": "5f23c031a51408243c1d05e9",

​        "position_ad_list": null

​      }

​    ]

  },

  "error_code": 1001,

  "msg": "get data success"

}
```

