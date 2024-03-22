# Query operaiton log

Query Conn operation log 

url:"/v1/cms/conn/getCommandList"

method:"get"

Need token or not: Need

Supported query parameters

field  type  instructions 

page int  currently page number, default is page 1 if not filled

pageSize int default is 10 if not filled

Example of return data from service side

//the filed that need to be showed _type  card_id state  date_created 

// omit other fileds

```
{

  "data": [

​    {

​      "_id": "6066d7a1a5140827d0379b80",

​      "_type": "EvaluationStars",

​      "account_id": "5f4777cfa51408189cb64d04",

​      "card_id": "1_taxi",

​      "date_created": "2021-04-02T16:36:49.977+08:00",

​      "deferred": true,

​      "sendTo": "joey-cardsystem",

​      "stars": 1,

​      "state": "Accept",

​      "user_id": "5f4777cfa51408189cb64d05"

​    },

  ],

  "error_code": 1000,

  "msg": "get command list success",

  "totalCount": 1

}
```

taxiapp operation log query 

url:"/v1/cms/log/getOperateTaxiAppLogList"

method:"get"

Need token or not: Need

Supported query parameters

field  type notes

page int  currently page number, default is page 1 if not filled

pageSize int default is 10 if not filled

Example of return data from service side

```
{

  "data": [

​    {

​      "device_list": [

​        "1_taxi"

​      ],          //devices list

​      "info": "userName:1226465969@qq.com,media_id:5f8eab01a514082394501355",         //notes information

​      "operation": "SetTaxiBackGround", //operation type

​      "date_created": "2021-05-07T11:34:32.082+08:00",  //create time

​      "is_success": true  //can omit

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 1

}

platform operation log query 

url:"/v1/cms/log/getUserOpLogList"

method:"get"

Need token or not: Need

Supported query parameters

field  type notes

page int  currently page number, default is page 1 if not filled

pageSize int  default is 10 if not filled

Example of return data from service side

{

  "data": [

​    {

​      "event": "login",   //event type

​      "info": "",      //note information 

​      "ip": "192.168.8.1",  //ip address

​      "username": "1226465969@qq.com", //user name

​      "date_created": "2021-05-08T10:10:56.488+08:00"    //create time

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 1

}
```

