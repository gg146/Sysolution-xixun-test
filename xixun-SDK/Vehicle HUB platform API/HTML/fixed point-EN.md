# region modem interfaces

 instructions 

 catalogue 

1.1 add a region

1.2update a region 

1.3delete a region

1.4get list

1.5get details

Interfaces

Add a region 

url:"/v1/cms/region/add"

method："post"

Need token or not: “Need”

Request data 

Field type instructions note 

name    string    region name, required

lat  string    latitude, required   

lng  string    longitude , required

radius    int  radius  unit meter

tag_id_list    string type’s array  tag id array, can be empty, but once filled, each item in the array must be the legal _id character string.

is_foreign bool  whether create in the google map, default is false 

response data 

```
{

  "error_code": 1002,

  "msg":  "create data success"

}
```

update region

url:"/v1/cms/region/:id/update"

method:"put"

Need token or not:”Need”

Request data

The same way with above interface, so omit.

response

```
{

  "error_code": 1003,

  "msg":  "update success"

}
```

Delete region

url:"/v1/cms/region/:id/delete"

method:"delete"

Need token or not:”Need”

Return data

```
{

  "error_code": 1004,

  "msg":  "delete success"

}
```

Get list page

url:"/v1/cms/region/list"

method:"get"

Need token or not:”Need”

Supported query parameters

Field type instructions 

page int  current page number, default is 1 if not filled

pageSize int  items in one page, default is 10 if not filled

is_foreign bool  whether created in the google map

tag_id_list    string    use English comma to divide several tag id

Return data

```
{

  "data": [

​    {

​      "id": "5ff2bb7ca5140838181ceacd",

​      "date_created": "2021-01-04T14:53:48.038+08:00",

​      "name": "xxxx",

​      "lat": "31.111111",

​      "lng": "123.1111111",

​      "currency": 0,

​      "radius": 10000,

​      "price": 0,

​      "is_foreign": false,

​      "allow_deleted": 0,

​      "tag_list":[]

​    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 1

}
```

