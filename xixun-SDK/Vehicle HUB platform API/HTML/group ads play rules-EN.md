# Group ads play rules

catalogue

Add rules

url:"/v1/cms/groupAdOrder/add"

method:"post"

Need token or not:Need

Request body parameters

Field type instructions

group_ad_id_list   string type’s array  required, an array of ad IDs, the length can not be empty 

Return data

```
{

  "error_code": 1002,

  "msg": "add success"

}
```

Modify rules

url:"/v1/cms/groupAdOrder/:id/update"

method:"put"

Need token or not: Need

Request body parameters

Field  type  instructions

group_ad_id_list   string type’s array, required, an array of ad IDs, the length can not be empty group_id_list  string type’s array  an array of group ids, can be empty

Return data

// to be added

Send rules to device

url:"/v1/cms/groupAdOrder/:id/send"

method:"put"

Need token or not: Need

Request body parameters

Field  type  instructions

group_id_list  string type’s array  an array of group ids, can not be empty

Return data

```
{

  "error_code": 11000,

  "msg": "send group ad success"

}

```

Get rules list 

url:"/v1/cms/groupAdOrder/list"

method:"get"

Need token or not: Need

Supported query parameters

Field  type  instructions

page int   default is 1 if not filled

pageSize int   default is 10 if not filled

Return data

```
{

  "data": [

​    {

​      "id": "5fea9b38a514082ec4a644a6",

​      "name": "xxxx",

​      "group_ad_id_list": [

​        "5fdacf2da5140804d865a34c"

​      ],  //an array of group ad IDs

​      "group_id_list": [], //an array of vehicle group

​      "status": "created", //status created，sent two types

​      "date_created": "2020-12-29T10:58:00.439+08:00"

​    },

​    {

​      "id": "5fea9aefa514082ec4a644a5",

​      "name": "xxxx",

​      "group_ad_id_list": [

​        "5fdacf2da5140804d865a34c"

​      ],

​      "group_id_list": [],

​      "status": "created",

​      "date_created": "2020-12-29T10:56:47.481+08:00"

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 2

}
```

Get rules details

url:"/v1/cms/groupAdorder/:id/detail"

method:"get"

Need token or not:Need

Returned data

```
{

  "data": {

​    "id": "5fea9b38a514082ec4a644a6",

​    "name": "xxxx",

​    "group_ad_id_list": [

​      "5fdacf2da5140804d865a34c"

​    ],

​    "group_id_list": [],

​    "status": "created",

​    "date_created": "2020-12-29T10:58:00.439+08:00",

​    "group_ad_list": [

​      {

​        "id": "5fdacf2da5140804d865a34c", //ad id

​        "name": "mmmmm"  //ad name      }

​    ],

​    "group_list": [

​      {

​      "id": "5fdacf2da5140804d865a34c", //vehicle group id

​       "name":"xxx111" //group name 

​    }

​    ],

​    "apply_device_id_list": [] //string type’s arrange, vehicles that received the rules

  },

  "error_code": 1001,

  "msg": "get data success"

}
```

Delete one rule

url:"/v1/cms/groupAdOrder/:id/delete"

mehtod:"delete"

Need token or not:Need

Returned data

```
{

  "error_code": 1004,

  "msg": "delete success"

}
```

