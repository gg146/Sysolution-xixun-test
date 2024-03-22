# Message push API 

 instructions 

 catalogue 

1.1添加一条通知 add a notification 

1.2修改一条通知 modify a notification

1.3删除一条通知delete a notification

1.4查看通知列表check notification list

1.5查看通知详情 check notification details

1.6发布通知post a notification

1.7用户实时获取消息 user get message in real time 

1.8用户获取所有收到的消息列表 user get all received message list 

1.9用户阅读一条消息 user read a message

1.10用户阅读所有的消息user read all messages

1.11用户删除一条消息user delete a message

1.12用户删除所有消息user delete all messages

Add a notification

url:"/v1/cms/notify/add"

method:"post"

Need token or not: Need

Front end requested json data

```
{

 "title":"platform has update",

  "body":"update some new functions",

  "send_method":"web", // web push  //mobile short message //email email notification 

  "message_type":"",

  "send_to":["xxxx","xxxxx"]  //userId

}
```

Back end returned json data

```
{

  "error_code":"1002",

  "msg":"add success",

}
```

Modify a notification

url:"/v1/cms/notify/:id/update"

method:"put"

Need token or not: Need

Front end requested json 

```
{

 "title":"platform has update",

  "body":"update some new functions",

"send_method":"web", // web push  //mobile short message //email email notification 

  "message_type":"xxx", //update message

  "send_to":["xxxx","xxxxx"]  //userId

}
```

Data back end returned json data

```
{

  "error_code":"1003",

  "msg":"modify success",

}
```

Delete a notification

url:"/v1/cms/notify/:id/delete"

method:"delete"

Need token or not:Need

Data back end returned json data

```
{

  "error_code":"1004",

  "msg":"delete success",

}
```

Check notification list 

url:"/v1/cms/notify/list"

method:"get"

Need token or not: Need

Front end requested json

Data back end returned json data

```
{

​    "error_code": 10000,

​    "msg":     "query success",

​    "totalCount": 1,

  "data":    [

​    {

​      "id":"xxxxx",    

​      "title":"platform push new content” ,//title

​      "message_body"："xxxxx", //message body

​      "message_type":"xxxx",  //message type

​      "send_method":"web",   //push type

​      "recipients":[      //recipients 

​       {"id":"xxx","username":"cxh"}

​       {"id":"xxx","username":"cxh2"}

​      ],

​      "has_read":[      //has read

​         {"id":"xxx","username":"cxh"}

​      ],

​      "unread":[       //unread

​         {"id":"xxx","username":"cxh2"}

​      ],

​      "has_send":true,    //has send or not

​      "date_created": "2020-08-12T09:44:28.476+08:00",

​      "send_at"："2020-08-12T09:44:28.476+08:00"    //wen has_send is false, this should be empty     }

  ],

}
```

Check notification details 

url:"/v1/cms/notify/:id/detail"

method:"get"

Need token or not: Need

Data back end returned json data

```
{

  "data": {

​    "id": "6049ac3ba51408141461e499",

​    "title": "platform updated",

​    "message_body": "update some new functions",

​    "message_type": "update message",

​    "send_method": "web",

​    "recipients": [

​      {

​        "id": "5f4777cfa51408189cb64d05",

​        "username": "1226465969@qq.com"

​      }

​    ],

​    "has_read": [],

​    "unread": [

​      {

​        "id": "5f4777cfa51408189cb64d05",

​        "username": "1226465969@qq.com"

​      }

​    ],

​    "has_send": false,

​    "date_created": "2021-03-11T13:43:39.063+08:00",

​    "send_at": null,

​    "use_web_when_miss": false,

​    "lng": ""

  },

  "error_code": 1001,

  "msg": "get data success"

}


```

Post notification 

url:"/v1/cms/notify/:id/send"

method:"get"

Need token or not:Need

Front end requested json

Data back end returned json data

```
{

  "error_code": 10002,

  "msg": "send message success"

}
```

User get message in real time 

url:"/v1/cms/getMessageRealTime"

method:"websocket persistent connection"

Need token or not: take token as query parameter auth_token=xxxx and joint it in url

Whether the server initiate to disconnect: No

Server return data in one time, example:

```
[

  {

  "body":"updated some new functions ",

   "has_read":false,

   "id":"6049ac3ba51408141461e499",

​    "title":"platform updated",

​    "type":"update message"

  }

]
```

 it could be an array or a single object 

 need to judge 

User get all received message list

url:"/v1/cms/message/list"

method:"get"

Need token or not:Need

Data back end returned json data

```
{

  "data": [

​    {

​      "body": "updated some new functions",

​      "has_read": false,

​      "id": "6049ac3ba51408141461e499",

​      "title": "platform updated",

​      "type": "update message"

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 1

}
```

User read a message

url:"/v1/cms/message/:id/readOneNotifyMessage"

method:"put"

Need token or not:Need

Data back end returned json data

```
{

  "error_code": 10000,

  "msg": "read notify message success"

}
```

User read all messages

url:"/v1/cms/message/readAllNotifyMessage"

method:"put"

Need token or not:Need

Data back end returned json data

```
{

  "error_code": 10000,

  "msg": "read notify message success"

}
```



User delete a message

url:"/v1/cms/message/:id/deleteOne"

method:"delete"

Need token or not:Need

Data back end returned json data

```
{

  "error_code": 10001,

  "msg": "clear notify message success"

}
```

User delete all messages

url:"/v1/cms/message/deleteAll"

method:"delete"

Need token or not:need

Data back end returned json data

```
{

  "error_code": 10001,

  "msg": "clear notify message success"

}
```

 