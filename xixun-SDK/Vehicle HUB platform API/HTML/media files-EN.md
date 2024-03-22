# Media file modem API

instructions

2020-08-12 modified return field, change return filed Type into type, add catalogue in the same time 

2020-11-23 newly added 1.5 1.6 1.7 1.8

catalogue

1.1upload media

1.2download media

1.3get file list

1.4delete file

1.5upload device parameters file

1.6download device parameters file

1.7 get device backup parameters file

1.8delete backup file

upload file 

url:"/v1/cms/media/upload"

method:"post"

Need token or not: Need

name = "files" in the form

Upload success and return 200, as it supports uploading multiple media files, so can not return information in detail

url:"/v1/cms/media/:id/download"

method:"get"

Need token or not:No

Download success and return the file directly

Get file list

url:"/v1/cms/media/list"

method:"get"

Need token or not: Need

Supported query parameters

Field  type  instructions

page int   default is 1 if not filled

pageSize int   default is 10 if not filled

media_type   int  Image、Gif 、Video、Audio、Zip Apk  corresponding to 0、1、2、3、4 ,

Keep value empty if want to get all types of media file

Response 

```
{

  "error_code":1001,

​    "msg":"get data success",

​    "totalCount":1,

  "data":[

​    {

​       "id": "5f33497ca514081150da2283",

​      "date_created": "2020-08-12T09:44:28.476+08:00",

​      "name": "64%20%E6%9B%B2%E7%9B%AE%2064 (1).mp3",

​      "md5": "845813fabb845e1a955d83fa85cc0583",

​      "size": 355528,

​      "type": "Audio"

​    }

  ]

}
```

Delete files

url:"/v1/cms/media/:id/delete"

method:"delete"

Need token or not: Need

Response information 

```
{

​    "error_code":1004,

​    "msg":"delete data success",

}


```

Upload device parameters file

url:"/v1/cms/media/uploadCscFile",

method:"post"

Need token or not: Need

name = "files" in the form

Response information: upload success and return 200

Download device parameters file

url :""/v1/cms/media/downloadCscFile""

method:"get"

Need token or not: No need

Download success and return the file

Get device backup parameters file list 

url:"/v1/cms/media/getCscFileList"

method :"get"

Need token or not: need 

Supported query parameters

Field  type  instructions 

page int  page number  default is 1 if not filled

pageSize int  items in one page, default is 10 if not filled

Returned data

```
{

  "data": [

​    {

​      "id": "5fbb19e4a514082b48daab39",

​      "date_created": "2020-11-23T10:09:40.426+08:00",

​      "name": "y10-999-00003.zip",

​      "md5": "e8b232daf24fab09d37819fa644263b9",

​      "size": 239042,

​      "type": "Csc"

​    },

​    {

​      "id": "5fbb1a9aa5140818606b6781",

​      "date_created": "2020-11-23T10:12:42.31+08:00",

​      "name": "y10-999-00003.zip",

​      "md5": "1668d0d2d2bf6ab8b71894f690e91067",

​      "size": 239047,

​      "type": "Csc"

​    },

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 2

}
```

Delete device backup files

url:"/v1/cms/media/:id/deleteCscFile"

method:"delete"

Need token or not: Need

Delete success and return data

```
{

  "error_code": 1004,

  "msg": "delete file success"

}
```

