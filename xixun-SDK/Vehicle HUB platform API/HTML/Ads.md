# Instructions of ads activity interfaces

catalogue

Add ads activity 

Update ads activity

Delete ads activity

ads activity list page

ads activity details page

Add ads activity

url: /v1/cms/positionAd/add

method:"post"

Need token or not: Need

Request data

field  type  instructions note

desc string    description of the ads, required    

media_type   int  material type, required, must be one of 0. 1. 2. 0 means static image, 1 means dynamic image 2 means video file

url  string    material download address required   

begin_at utc time（can be change into timestamp） available time，required    

end_at   utc time(can be change into timestamp)    disable time, required  

container_list object array  as in  below:        

```
{

  container_list:[

​    {

​    "container_id":"5dd64514a514083cecbc7344",   //container id

​    "floor_id":"5dd64514a514083cecbc7342"     //container floor id(that is ads unit id)

  }

  ]

}
```

//this object is also required, The two ID fields in each object in the array must be legal

Response data 

```
{

  "error_code": 1002,

​    "msg":    "add data success" 

}
```

Update ads activity

url:"/v1/cms/positionAd/:id/update"

method:"put"

Need token or not: Need

Request data

field  type  instructions note

media_url    string    media type, required

Response data

```
{

​    "error_code": 1003,

​    "msg":    "modify success",

}
```

Delete ads activity 

url:/v1/cms/positionAd/:id/delete

method:"delete"

Need token or not: Need

Response data

```
{

  "error_code": 1004,

​    "msg":    "success to delete data",

}
```

Ads list 

url:/v1/cms/positionAd/list

method:"get"

Need token or not: Need

Supported to query parameters（can add more if not enough）

field  type  instructions

page int  pagination, default is 1 if not filled

pageSize int  default is 10 if not filled

Response data

```
{

  "data": [

​    {

​      "id": "5f27b2c7a5140830047cc936",

​      "desc": "11111",

​      "container_list": [

​        {

​          "container_id": "5f27a353a51408339cb734d1",

​          "floor_id": "5f27a353a51408339cb734d2"

​        }

​      ],

​      "MediaType": 0,

​      "media_url": "https://www.baidu.com",

​      "begin_at": "2020-09-01T00:00:00+08:00",

​      "end_at": "2020-10-01T00:00:00+08:00",

​      "date_created": "2020-08-03T14:46:31.025+08:00"

​    },

​    {

​      "id": "5f27b249a5140830047cc935",

​      "desc": "11111",

​      "container_list": [

​        {

​          "container_id": "5f27a353a51408339cb734d1",

​          "floor_id": "5f27a353a51408339cb734d2"

​        }

​      ],

​      "MediaType": 0,

​      "url": "https://www.baidu.com",

​      "begin_at": "2020-07-01T00:00:00+08:00",

​      "end_at": "2020-08-01T00:00:00+08:00",

​      "date_created": "2020-08-03T14:44:25.119+08:00"

​    }

  ],

   "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 2

}

Ads details page

url:"/v1/cms/positionAd/:id/detail"

method:get

Need token or not: Need

Return data

{

  "data": {

​    "id": "5f27b2c7a5140830047cc936",

​    "desc": "11111",

​    "container_list": [

​      {

​        "container_id": "5f27a353a51408339cb734d1",

​        "floor_id": "5f27a353a51408339cb734d2"

​      }

​    ],

​    "media_type": 0,

​    "media_url": "https://www.baidu.com",

​    "begin_at": "2020-09-01T00:00:00+08:00",

​    "end_at": "2020-10-01T00:00:00+08:00",

​    "date_created": "2020-08-03T14:46:31.025+08:00"

  },

  "error_code": 1001,

  "msg": "get data success"

}
```

