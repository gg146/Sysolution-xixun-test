# region tag modem

instructions 

 catalogue

1.1 add a tag

1.2modify a tag

1.3delete a tag

1.4get list 

catalogue 

 add a tag

url:"/v1/cms/regionTag/add"

method:"post"

Need token or not: Need

Request body data

Filed type instructions note

name    string    required option 

 response 

```
{

  "error_code": 1002,

  "msg":    "add data success"

}
```

 modify a tag

url:"/v1/cms/regionTag/:id/update"

method:"put"

Need token or not: Need

Request data

Same like add a tag

 response

```
{

  "error_code": 1003,

  "msg":    "modify data success"

}
```

 delete a tag

url:"/v1/cms/regionTag/:id/delete"

method:"delete"

Need token or not: Need

response

```
{

  "error_code": 1004,

  "msg":    "modify data success"

}
```

Get list

url:"/v1/cms/regionTag/list"

method:"get"

Need token or not: Need

Supported query parameters

Field  type  instructions 

page int default is 1 

pageSize int   default is 10

Response data

```
{

  "data": [

​    {

​      "id": "5f24f40ba5140834cc95e845",

​      "date_created": "2020-08-01T12:48:11.52+08:00",

​      "name": "a small test"

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 1
  }
```

