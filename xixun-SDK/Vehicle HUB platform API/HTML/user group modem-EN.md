>

# User group modem API

Instructions

Normally require admin right to use those API except during debug process

catalogue

1.1 add s user group

1.2 delete a user group

1.3 update user group

1.4 get user group list page

1.5 get user group details page

1.6 get permission information 

Add a user group

url :/v1/cms/userGroup/add

method:post

Need token or not: Need

request body parameters

Field  type  instructions  note 

group_name  string    group name    

permissions   object  form as in below    

```
{

​     //will submit the options that user selects

​    //refer to getPermission get detailed data

​    "modules":["dashboard"，"map"，"fixed point"]， 

​    “actions:["get gps track"，"get map and vehicle information"]

}
```

Response 

```
{

  "msg":"add success",

  "error_code":1002

}
```

Delete a user group 

url::/v1/cms/userGroup/:id/delete

method:delete

Need token or not: Need

response

```
{

  "msg":"delete success",

  "error_code":1004

}
```

Update a user group

url::/v1/cms/userGroup/:id/update

method:put

Need token or not: Need

response

```
{

  "msg":"update success",

  "error_code":1003

}
```

Get user group list

url:/v1/cms/userGroup/list

method:get

Need token or not: Need

Supported query parameters

field  type  instructions

page int  default is one page if not filled

pageSize int  get 10 pieces of data if not filled

response

```
{

  "data": [

​    {

​      "id": "6030b4f6a514088430269802",

​      "group_name": "xxxxx",

​      "is_root": false,

​      "is_admin": false,

​      "user_scope": "common_scope",

​      "permissions": null

​    },

​    {

​      "id": "6030b4d2a514088430269801",

​      "group_name": "xxxxx",

​      "is_root": false,

​      "is_admin": false,

​      "user_scope": "common_scope",

​      "permissions": null

​    },

​    {

​      "id": "6030b1bda5140874445632dd",

​      "group_name": "xxxxx",

​      "is_root": false,

​      "is_admin": false,

​      "user_scope": "common_scope",

​      "permissions": null

​    },

​    {

​      "id": "5f4777cfa51408189cb64d06",

​      "group_name": "Super Group",

​      "is_root": false,

​      "is_admin": true,

​      "user_scope": "admin_scope",

​      "permissions": null

​    }

  ],

  "error_code": 1000,

  "msg": "get user group data success",

  "totalCount": 4

}
```

Get user group details page

url:/v1/cms/userGroup/:id/detail

method:get

Need token or not: Need

response

```
{

  "data": {

​    "id": "5f4777cfa51408189cb64d06",

​    "group_name": "Super Group",

​    "is_root": false,

​    "is_admin": true,

​    "user_scope": "admin_scope",

​    "permissions": {

​      "actions": [

​        {

​          "add group ads": true

​        },

​        {

​          "delete group ads": true

​        },

​        {

​          "group ads list": true

​        },

​        {

​          "update group ads": true

​        },

​        {

​          "group ads details": true

​        },

​        {

​          "refresh group ads post status": true

​        },

​        {

​          "refresh group ads terminate status": true

​        },

​        {

​          "release group ads": true

​        },

​        {

​          "cancel release group ads": true

​        },

​        {

​          "cancel terminate group ads": true

​        },

​        {

​          "update group ads release date and time": true

​        },

​        {

​          "terminate group ads": true

​        },

​        {

​          "update group ads terminate date and time": true

​        },

​        {

​          "download group ads released report": true

​        },

​        {

​          "download group ads terminated report": true

​        },

​        {

​          "reset the groups of group ads": true

​        },

​        {

​          "add group ads sort": true

​        },

​         {

​            "update group ads sort": true

​          },

​          {

​            "group ads sort list": true

​          },

​          {

​            "group ads sort details": true

​          },

​          {

​            "get vehicle on the map": true

​          },

​          {

​            "get gps track information": true

​          },

​          {

​            "download media file": true

​          },

​          {

​            "media file list ": true

​          },

​          {

​            "upload media file": true

​          },

​          {

​            "delete media file": true

​          },

​          {

​            "add fixed point": true

​          },

​          {

​            "update fixed point": true

​          },

​          {

​            "fixed point list": true

​          },

​          {

​            "fixed point details": true

​          },

​          {

​            "delete fixed point": true

​          },

​          {

​            "fixed point ads list": true

​          },

​          {

​            "fixed point ads details": true

​          },

​          {

​            "add fixed point ads": true

​          },

​          {

​             "update fixed point ads": true

​          },

​          {

​            "delete fixed point ads": true

​          },

​          {

​            "release fixed point ads": true

​          },

​          {

​            "get fixed point ads play log": true

​          },

​          {

​            "add quantity ads": true

​          },

​          {

​            "quantity ads list": true

​          },

​          {

​            "release quantity ads": true

​          },

​          {

​            "delete quantity ads": true

​          },

​          {

​            "terminate quantity ads ": true

​          },

​          {

​            "get quantity ads release details": true

​          },

​          {

​            "get quantity ads terminate details": true

​          },

​          {

​            "update quantity ads": true

​          },

​          {

​            "cancel releasing quantity ads": true

​          },

​          {

​            "update release date and time for quantity ads": true

​          },

​          {

​            "cancel terminate quantity ads": true

​          },

​          {

​            "get quantity ads received details": true

​          },

​          {

​            "vehicle group": true

​          },

​          {

​            "delete vehicle group ": true

​          },

​          {

​            "vehicle group list": true

​          },

​          {

​            "add vehicle group": true

​          },

​          {

​            "update vehicle group": true

​          },

​          {

​            "vehicle group details": true

​          },

​          {

​            " add vehicle to the group": true

​          },

​          {

​            "remove vehicle from the group": true

​          },

​          {

​            "vehicle list": true

​          },

​          {

​            "get vehicle details": true

​          },

​          {

​            "screen shot": true

​          },

​          {

​            "screenshot by camera": true

​          },

​          {

​            "android full size screenshot": true

​          },

​          {

​            "query screen brightness": true

​          },

​          {

​            "set brightness by manual": true

​          },

​          {

​            "set auto brightness": true

​          },

​          {

​            "add brightness schedule task": true

​          },

​          {

​            "brightness schedule task list": true

​          },

​          {

​            "delete brightness schedule task": true

​          },

​          {

​            "modify brightness schedule task": true

​          },

​          {

​            "send brightness schedule task": true

​          },

​          {

​            "query screen switch": true

​          },

​          {

​            "set screen switch by manual": true

​          },

​           {

​            "add screen switch schedule task": true

​          },

​          {

​            "delete screen switch schedule task": true

​          },

​          {

​            "modify screen switch schedule task": true

​          },

​          {

​            "screen switch schedule task list": true

​          },

​          {

​            "send screen switch schedule task": true

​          },

​          {

​            "query parameters": true

​          },

​          {

​            "query GPS": true

​          },

​          {

​            "query sync information": true

​          },

​          {

​            "set sync": true

​          },

​          {

​            "send backup command": true

​          },

​          {

​            "upload restore file zip": true

​          },

​          {

​            "delete restore file zip": true

​           },

​          {

​            "download restore file zip": true

​          },

​          {

​            "send restore command": true

​          },

​          {

​            "query volume": true

​          },

​          {

​            "set volume by manual": true

​          },

​          {

​            "add volume schedule task": true

​          },

​          {

​            "delete volume schedule task": true

​          },

​          {

​            "modify volume schedule task": true

​          },

​          {

​            "volume schedule task list": true

​          },

​          {

​            "send volume schedule task": true

​          },

​          {

​            "query hardware status": true

​          },

​          {

​            "upload zip": true

​          },

​          {

​            "delete zip": true

​          },

​          {

​            "download zip": true

​          },

​          {

​            "send updating software version command": true

​          },

​          {

​            "uninstall software version": true

​          },

​          {

​            "get updating list details": true

​          },

​          {

​            "conn server config": true

​          },

​          {

​            "update vehicle information": true

​          },

​          {

​            "update vehicle information in bulk": true

​          },

​          {

​            "download sample file of update vehicle information": true

​          },

​          {

​            "set customized display": true

​          },

​          {

​            "transfer in bulk": true

​          },

​           {

​            "delete terminal": true

​          },

​          {

​            "get terminal quantities": true

​          },

​          {

​            "export offline terminal reports": true

​          },

​          {

​            "download vehicle access certificate": true

​          },

​          {

​            "download IMSI list": true

​          }

​        ],

​        "modules": [

​          {

​            "dashboard": true

​          },

​          {

​            "media management": true

​          },

​          {

​            "map": true

​          },

​          {

​            "device management": true

​          },

​          {

​            "group ads": true

​          },

​          {

​            "fixed point ads": true

​          },

​          {

​            "quantities ads": true

​        }

​      ]

​    }

  },

  "error_code": 1001,

  "msg": "get user group success"

}

}
```

Get permission information

url:"/v1/cms/userGroup/getPermissionList"

method:"get"

Need token or not: Need

Return data

```
{

  "data": {

​    "group ads": [

​      "delete group ads",

​      "group ads list",

​      "update group ads",

​      "group ads detail",

​      "refresh group ads release status",

​      "refresh group ads terminate status",

​      "release group ads",

​      "cancel release group ads",

​      "cancel terminate group ads",

​      "update group ads release date and time",

​      "terminate group ads",

​      "update group ads terminate date and time",

​      "download group ads released report",

​      "download group ads terminated report",

​      "reset the groups of group ads",

​      "add group ads sort",

​      "update group ads sort",

​      "group ads sort list page",

​      "group ads sort details"

​    ],

​    "map": [

​      "get vehicle on the map",

​      "get gps track information"

​    ],

​    "media management": [

​      "download media file",

​      "media file list page",

​      "upload media file",

​      "delete media file"

​    ],

​    " fixed point": [

​      "fixed point list page",

​      "fixed point list details page",

​      "add fixed point",

​      " update fixed point",

​      "delete fixed point",

​       "release fixed point",

​      "get fixed point ads play log"

​    ],

​    "quantity ads": [

​      "add quantity ads",

​      "quantity ads list page",

​      "release quantity ads",

​      "delete quantity ads",

​       "terminate quantity ads",

​      "get quantity ads release details",

​      "get quantity ads terminate details",

​      "update quantity ads",

​      "cancel releasing quantity ads",

​      "update release date and time for quantity ads",

​      "cancel terminate quantity ads",

​      "get quantity ads received details"

​    ],

​    "terminal management": [

​      "vehicle group",

​      "delete vehicle group",

​      "vehicle group list",

​      "add vehicle group",

​      "update vehicle group",

​      "vehicle group details",

​      "add vehicle to the group",

​      "remove vehicle from the group",

​      "vehicle list",

​      "get vehicle details",

​      "screen shot",

​      "screenshot by camera",

​      "android full size screenshot",

​      "query screen brightness",

​      "set brightness by manual",

​      "set auto brightness",

​      "add brightness schedule task",

​      "brightness schedule task list",

​      "delete brightness schedule task",

​      "modify brightness schedule task",

​      "send brightness schedule task",

​      "query screen switch",

​      "set screen switch by manual",

​      "add screen switch schedule task",

​      "delete screen switch schedule task",

​      "modify screen switch schedule task",

​      "screen switch schedule task list page",

​      "send screen switch schedule task",

​      "query parameters",

​      "query GPS",

​      "query sync information",

​      "set sync",

​      "send backup command",

​      "upload restore file zip",

​      "delete restore zip",

​      "download restore file zip",

​      "send restore command",

​      "query volume",

​      "set volume by manual",

​      "add volume schedule task",

​      "delete volume schedule task",

​      "modify volume schedule task",

​      "volume schedule task list",

​      "send volume schedule task",

​      "query hardware status",

​      "upload zip",

​      "delete zip",

​      "download zip",

​      "send updating software version command",

​       "uninstall software version",

​      "get updating details list",

​      "conn server config",

​      "update vehicle information",

​      "update vehicle information in bulk",

​      "download sample file of update vehicle information",

​      "set customized display",

​      "transfer in bulk",

​      "delete terminal",

​      "get terminal quantities",

​      "export offline terminal reports",

​      "download vehicle access certificate",

​      "download IMSI list"

​    ]

  },

  "error_code": 1001,

  "msg": "success"

}
```

