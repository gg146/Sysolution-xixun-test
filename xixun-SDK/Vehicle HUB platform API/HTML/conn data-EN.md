# Conn data interfaces 

Instructions

Catalogue 

1.1add screen switch on schedule task data

1.2modify screen switch on schedule task

1.3screen switch on schedule task list

1.4screen switch on schedule task details 

1.5delete screen switch on schedule task

2.1add screen brightness schedule task data

2.2modify screen brightness schedule task 

2.3delete screen brightness schedule task 

2.4screen brightness schedule task list page

2.5screen brightness schedule task details 

3.1add volume schedule task 

3.2modify volume schedule task

3.3delete volume schedule task

3.4Get volume schedule task list 

3.5Get volume schedule task details 

4.1query command records command 

4.2query and get the process of upgrade apk command, original interface url is /QueryUpdateApkStatus

Screen switch on schedule task 

add screen switch on schedule task data

url:"/v1/cms/keepScreenOnTask/add"

method:"post"

Need a token or not: Need 

Example of front end post data:

```
{



  "name": "qwer",

  "lng": "zh-CN",

  "schedules": [{

​    "lng": "zh-CN",

​    "monthFilter": [],

​    "weekFilter": [],

​    "filterType": "None",

​    "endTime": null,

​    "startTime": null,

​    "timeType": "All",

​    "endDate": null,

​    "startDate": null,

​    "dateType": "All"

  }]

}
```

Example: back end return data

```
{

 "error_code": 1002,

  "msg":  "create data success

}
```

modify screen switch on schedule task

url:"/v1/cms/keepScreenOnTask/:id/update"

method:"put"

Need a token or not: Need

Front end post data, example:

```
{

  "name": "qwer",

  "lng": "zh-CN",

  "schedules": [{

​    "lng": "zh-CN",

​    "monthFilter": [],

​    "weekFilter": [],

​    "filterType": "None",

​    "endTime": null,

​    "startTime": null,

​    "timeType": "All",

​    "endDate": null,

​    "startDate": null,

​    "dateType": "All"

  }]

}
```

Back end return data, example:back end return data

```
{

  "error_code": 1003,

  "msg":  "update success”

}
```

screen switch on schedule task list

url:"/v1/cms/keepScreenOnTask/list"

method:"get"

Need a token or not: Need

Supported query parameters:

field  type  instructions

page int  default is 1 if not filled in

pageSize int  default is 10 if not filled in

Back end return data, example:back end return data

```
{

  "error_code": 1000,

  "msg": "get data success",

  "totalCount": 1,

  "data": [{

​    "_id": "5e86d9e6a5140847b4485e56",

​    "name": "asdasdas",

​    "dateCreated": "2020-04-03T06:38:30.323Z",

​    "lng": "zh-cn",

​    "Schedules": [{

​      "lng": "zh-cn",

​      "monthFilter": [],

​      "weekFilter": [],

​      "filterType": "Week",

​      "endTime": "18:00",

​      "startTime": "00:00",

​      "timeType": "Range",

​      "endDate": "2020-04-30",

​      "startDate": "2020-04-03",

​      "dateType": "Range"

​    }]

  }]

}
```

screen switch on schedule task details

url:"/v1/cms/keepScreenOnTask/:id/detail"

method:"get"

Need a token or not: Need

back end return data

```
{

  "error_code": 1001,

  "msg": "get data success",

  "data":{

​    "_id": "5e86d9e6a5140847b4485e56",

​    "name": "asdasdas",

​    "dateCreated": "2020-04-03T06:38:30.323Z",

​    "lng": "zh-cn",

​    "Schedules": [{

​      "lng": "zh-cn",

​      "monthFilter": [],

​      "weekFilter": [],

​      "filterType": "Week",

​      "endTime": "18:00",

​      "startTime": "00:00",

​      "timeType": "Range",

​      "endDate": "2020-04-30",

​      "startDate": "2020-04-03",

​      "dateType": "Range"},  

}
```

Delete screen switch on schedule task

url:"/v1/cms/keepScreenOnTask/:id/delete"

method:"delete"

Need a token or not: Need

back end return data

```
{

  "error_code": 1004,

  "msg":  "delete success"

}
```

Screen brightness schedule task 

Add screen brightness schedule task data

url:"/v1/cms/brightnessesTask/add"

method:"post"

Need a token or not: Need

front end post data

```
{

  "defaultBrightness": 5,

  "name": "asdasd",

  "lng": "zh-CN",

  "items": [{

​    "brightness": 5,

​    "schedules": [{

​      "lng": "zh-cn",

​      "dateType": "All",

​      "startDate": null,

​      "endDate": null,

​      "timeType": "All",

​      "startTime": null,

​      "endTime": null,

​      "filterType": "None",

​      "weekFilter": [],

​      "monthFilter": []

​    }]

  }]

}
```

back end return data

```
{

 "error_code": 1002,

  "msg":  "create data success"

}
```

Modify screen brightness schedule task 

url:"/v1/cms/brightnessesTask/:id/update"

method:"put"

Need a token or not: Need

front end post data

```
{

  "defaultBrightness": 5,

  "name": "asdasd",

  "lng": "zh-CN",

  "items": [{

​    "brightness": 5,

​    "schedules": [{

​      "lng": "zh-cn",

​      "dateType": "All",

​      "startDate": null,

​      "endDate": null,

​      "timeType": "All",

​      "startTime": null,

​      "endTime": null,

​      "filterType": "None",

​      "weekFilter": [],

​      "monthFilter": []

​    }]

  }]

}
```

back end return data

```
{

  "error_code": 1003,

  "msg":  "update success"

}
```

Delete screen brightness schedule task 

url:"/v1/cms/brightnessesTask/:id/delete"

method:"delete"

Need a token or not: Need

back end return data

```
{

  "error_code": 1004,

  "msg":  "delete success"

}
```

screen brightness schedule task list page

url:"/v1/cms/brightnessesTask/list"

method:"get"

Need a token or not: Need

Supported query parameters

field type  instructions

page int  default is 1 if not filled in

pageSize int  default is 10 if not filled in

back end return data

```
{

  "error_code": 1000,

  "msg": "get data success",

  "totalCount": 1,

  "request_url": "",

  "data": [{

​    "_id": "5e89bdf18283968413a4503d",

​    "defaultBrightness": 5,

​    "items": [{

​      "brightness": 5,

​      "_id": "5e89bdf18283968413a4503e",

​      "schedules": [{

​        "lng": "zh-CN",

​        "monthFilter": [],

​        "weekFilter": [

​          0,

​          1,

​          2,

​          3,

​          4,

​          5

​        ],

​        "filterType": "Week",

​        "endTime": "18:30",

​        "startTime": null,

​        "timeType": "Range",

​        "endDate": "2020-04-22",

​        "startDate": "2020-04-06",

​        "dateType": "Range"

​      }]

​    }],

​    "dateCreated": "2020-04-05T11:16:01.626Z"

  }]

}
```

Screen brightness schedule task details 

url:"/v1/cms/brightnessesTask/:id/detail"

method:"get"

Need a token or not: Need

back end return data

```
{

  "error_code": 1001,

  "msg": "query success",

  "request_url": "",

  "data": {

​    "_id": "5e89bdf18283968413a4503d",

​    "defaultBrightness": 5,

​    "name": "qwert",

​    "items": [{

​      "brightness": 5,

​      "_id": "5e89bdf18283968413a4503e",

​      "schedules": [{

​        "lng": "zh-CN",

​        "monthFilter": [],

​        "weekFilter": [

​          0,

​          1,

​          2,

​          3,

​          4,

​          5

​        ],

​        "filterType": "Week",

​        "endTime": "18:30",

​        "startTime": null,

​        "timeType": "Range",

​        "endDate": "2020-04-22",

​        "startDate": "2020-04-06",

​        "dateType": "Range"

​      }]

​    }],

​    "dateCreated": "2020-04-05T11:16:01.626Z"

  }

}
```

Volume schedule task

Add Volume schedule task

url:"/v1/cms/volumeTask/add"

method:"post"

Need a token or not: Need

front end post data

```
{

  "name": "111111",

  "defaultVolume": 10,

  "lng": "zh-cn",

  "items": [{

​    "volume": 15,

​    "schedules": [{

​      "lng": "zh-cn",

​      "monthFilter": [],

​      "weekFilter": [],

​      "filterType": "None",

​      "endTime": null,

​      "startTime": null,

​      "timeType": "All",

​      "endDate": null,

​      "startDate": null,

​      "dateType": "All"

​    }]

  }]

}
```

back end return data

```
{

 "error_code": 1002,

 "msg":  "create data success"

}
```

Modify Volume schedule task

url:"/v1/cms/volumeTask/:id/update"

method:"put"

Need a token or not: Need

front end post data

```
{

  "name": "111111",

  "defaultVolume": 10,

  "lng": "zh-cn",

  "items": [{

​    "volume": 15,

​    "schedules": [{

​      "lng": "zh-cn",

​      "monthFilter": [],

​      "weekFilter": [],

​      "filterType": "None",

​      "endTime": null,

​      "startTime": null,

​      "timeType": "All",

​      "endDate": null,

​      "startDate": null,

​      "dateType": "All"

​    }]

  }]

}
```

back end return data

```
{

  "error_code": 1003,

  "msg":  "update success"

}
```

Delete Volume schedule task

url:"/v1/cms/volumeTask/:id/delete"

method:"delete"

Need a token or not: Need

front end post data

back end return data

```
{

  "error_code": 1004,

  "msg":  "delete success"

}
```

Get Volume schedule task list

url:"/v1/cms/volumeTask/list"

method:"get"

Need a token or not: Need

front end post data

field  type  instructions

page int  default is 1 if not filled in

pageSize int  default is 10 if not filled in

back end return data

```
{

  "error_code": 1001,

  "msg": "get data success",

  "totalCount": 1,

  "request_url": "",

  "data": [{

​    "_id": "5e85aab7a5140809c0141e42",

​    "name": "111111",

​    "defaultVolume": 10,

​    "items": [{

​      "_id": "5e85aab7a5140809c0141e41",

​      "volume": 15,

​      "schedules": [{

​          "monthFilter": [],

​          "weekFilter": [],

​          "filterType": "None",

​          "endTime": null,

​          "startTime": null,

​          "timeType": "All",

​          "endDate": null,

​          "startDate": null,

​          "dateType": "All"

​        },

​        {

​          "monthFilter": [],

​          "weekFilter": [],

​          "filterType": "None",

​          "endTime": null,

​          "startTime": null,

​          "timeType": "All",

​          "endDate": null,

​          "startDate": null,

​          "dateType": "All"

​        }

​      ]

​    }],

​    "dateCreated": "2020-04-02T09:04:55.428Z"

  }]

}
```

Get volume schedule task details 

url:"/v1/cms/volumeTask/:id/detail"

method:"get"

Need a token or not: Need

back end return data

```
{

  "error_code": 1001,

  "msg": "query success",

  "data": {

​    "_id": "5e85aab7a5140809c0141e42",

​    "name": "111111",

​    "defaultVolume": 10,

​    "items": [{

​      "_id": "5e85aab7a5140809c0141e41",

​      "volume": 15,

​      "schedules": [{

​          "monthFilter": [],

​          "weekFilter": [],

​          "filterType": "None",

​          "endTime": null,

​          "startTime": null,

​          "timeType": "All",

​          "endDate": null,

​          "startDate": null,

​          "dateType": "All"

​        }

​      ]

​    }],

​    "dateCreated": "2020-04-02T09:04:55.428Z"

  }

}
```

conn_command

Query command sending records

url:"/v1/cms/conn/getCommandList"

method:"get"

Need a token or not: Need

Supported query parameters

field  type  instructions

page int  default is 1 if not filled in

pageSize int  default is 10 if not filled in

_type    string    all command types in conn modem

Back end return data

```
{

  "data": [

​    {

​      "id": "5f6c7212a514082c68c994ff",

​      "state": "Success",

​      "_type": "GetSync",

​      "date_created": "2020-09-24T18:16:50.969+08:00",

​      "deferred": false,

​      "card_id": "y30-120-01093",

​      "error_message": ""

​    },

  ],

  "error_code": 1000,

  "msg": "get command list success",

  "totalCount": 1

}
```

//when state is  Error, means error_message should has value, it should be show up in page at this moment. 

//when state is Success,means successful

//command’s all state

// Accept means the server received this command

//Deny   the command invalid or expired

// Success controller received and executed success

//Error  Any exception that occurs during the sending of this command 

// Received controller received the command but not execute yet

// Timeout send command time out

// Offline device offline

query and get the process of upgrade apk command, original interface url is /QueryUpdateApkStatus

url:complete url is：/v1/cms/conn/queryUpdateApkStatus?auth_token=xxx&commandId=xxxxx

method:websocket long connection

Need a token or not: Need. You can put the token in the request head or put it in query parameters, pls check above completed url for reference. 

Is the server actively disconnected: Yes

Status 1: when process reaching 100%, server actively disconnect

Status2: when controller return some exceptions

Status3: the server will actively disconnect if did not receive return data from device at specific time range (5 minutes )

Status4: Do not have token or lack of command or the query parameters on the URL when commandid illegally establishes a connection

field  type  instructions   notes

auth_token   string    token   If don't fill in here, you need to put the token in the request header, just like other interfaces that need to carry a token. Choose either one. 

commandId   string    specific command id that need to query     must fill in, or disconnect directly 

Single data return from server, example: 

```
{

  "commandId":"5f87dee6a5140826f41c10ea",

  "speed":1861,      

  "unzipped":true,

  "State":"Success",

  "progress":100,

}
```

