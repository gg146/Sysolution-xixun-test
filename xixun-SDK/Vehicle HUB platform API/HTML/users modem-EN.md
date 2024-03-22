# User modem API

preface

For the API in below only for request success, for failed, please refer to the error_code in the code.js and find the specific error. 

If there is no instructions in the error_code of code.js, please contact us.

API catalogue

1.1 user register 

1.2 user login

1.3 check email address already occupied

1.4 user change new password

 1.5 get the current login user information

 1.6 administrator add another user

 1.7 administrator update a user

 1.8 administrator get user list

 1.9 administrator delete a user

 1.10administrator get user detail information

 1.11user update own information  

1.12 refresh token 

1.13 download vehicle access certificate  

1.14 reset password by email 

1.15 send verification code

 1.16 phone number register

1.1 user register

url:/v1/cms/user/register

method:post

Request body parameters

Field   type  instructions     required or not 

email    string    use email as the login id  required

password string    password,   at least 8 characters including numbers,   required

verify_code   string    email verification code, no need verify currently, but need leave email address,  temporally not required

Response 

//response success

```
{

  "error_code":1100 ,  //error code，int type

  "msg":"register success",

  "data":{

​    "access_token":"eyJhbGciOiJIUzI1NiIsInR5cCI",

​    "refresh_token":"eyJhbGciOiJIUzI1NiIs"

  },

  "permissions":{

​    //left sidebar

​    "actions":{"add media":true,"delete media":false},

​    //Elements of various requests on the page

​    "modules":{"media management":true,"user management"：false}

  },

 "user_scope":"admin_scope", 

}
```

1.2 user login 

url:"/v1/cms/user/login"

method:"post"

request body parameters

Field   type  instructions     required or not

username    string         required

password string         required

Response

Same like user register response, so jump it. Except error_code and msg are different, error_code is

1.3check user name is already existed

url:/v1/cms/user/checkAccountExisted

method:"post"

Need token or not：No need

Request parameters

Field   type  instructions     required or not

username    string         yes

Response

//not existed

```
{

  "data": {

​    "existed": false

  },

  "error_code": 1001,

  "msg": "not occupied"

}


```

//existed

```
{

  "data": {

​    "existed": true

  },

  "error_code": 1001,

  "msg": "occupied"

}
```

User reset password

url:"/v1/cms/user/UpdatePassword"

method:"post"

Need token or not: need

request parameters

Field   type  instructions     required or not

new_password    string    new password, at least 8 characters, required

row_password string    original password, required

Response ：

```
{

 "error_code":1003,

  "msg":"change new password success" 

}
```

Administrator add new user

url :"/v1/cms/user/add",

method:"post"

Need token or not: Need

request body parameters

Field   type  instructions     required or not

username    string    user name   required    

user_type    string    user type     //required mobile or Email

password string    password  required 

mobile   string    mobile   when user_type is email required  no need input this field 

nick_name    string    nickname  not required

group_id string    group id      required

 Response 

```
{

  "error_code": 1002,

  "msg":     " add success",

}
```

Administrator update a user

url:/v1/cms/user/:id/update

method:"put"

Need token or not: Need

request body parameters

Field   type  instructions     required or not

nick_name    string    nickname    not required    

group_id string    group id        required

Response 

```
{

  "error_code":1003,

  "msg":"update success"

}
```

Get user list 

url:"/v1/cms/user/list",

method:"get"

Need token or not: Need

Supported query parameters

Field  instructions   

groupId  character string type, get all user if not filled

page  value type, default to get first page data if not filled 

pageSize  default is 10 pieces of data in one page if not filled 

Need token or not: Need

Response 

```
{

  "data": [

​    {

​      "id": "5f4777cfa51408189cb64d05",

​      "username": "1226465969@qq.com",

​      "email": "1226465969@qq.com",

​      "nick_name": "",

​      "mobile": "",

​      "disabled": false,

​      "user_group": {

​        "id": "5f4777cfa51408189cb64d06",

​        "group_name": "Super Group",

​        "is_root": false,

​        "is_admin": true,

​        "user_scope": "admin_scope",

​        "permissions": null //list page not allowed to show

​      },

​      "register_type": "email"

​    }

  ],

  "error_code": 1000,

  "msg": "query user list success",

  "totalCount": 1

}

Administrator delete a user

url:"/v1/cms/user/:id/delete"

method:delete

Need token or not: Need

response

{

  "error_code":1004,

  "msg":"delete success"

}

Administrator get user detail information 

url:/v1/cms/user/:id/detail

method:"get"

need token or not: Need

response

{

  "data": {

​    "id": "5f4777cfa51408189cb64d05",

​    "username": "1226465969@qq.com",

​    "email": "1226465969@qq.com",

​    "nick_name": "",

​    "mobile": "",

​    "disabled": false,

​    "user_group": {

​      "id": "5f4777cfa51408189cb64d06",

​      "group_name": "Super Group",

​      "is_root": false,

​      "is_admin": true,

​      "user_scope": "admin_scope",

​      "permissions": {

​        "actions": [

​          {

​            "add group ads": true

​          },

​          {

​            "delete group ads": true

​          },

​          {

​            "group ads list": true

​          },

​          {

​            "update group ads": true

​          },

​          {

​            "group ads detail": true

​          },

​          {

​            "refresh group ads release status": true

​          },

​          {

​            "refresh group ads terminate status": true

​          },

​          {

​            "release group ads": true

​          },

​          {

​            "cancel release group ads": true

​           },

​          {

​            "cancel terminate group ads": true

​          },

​          {

​            "update group ads release date and time": true

​          },

​          {

​            "terminate group ads": true

​          },

​          {

​            "update group ads terminate date and time": true

​          },

​          {

​             "download group ads released report": true

​          },

​          {

​            "download group ads terminated report": true

​          },

​          {

​            "reset the groups of group ads": true

​          },

​          {

​            "add group ads sort": true

​          },

​          {

​            "update group ads sort": true

​          },

​          {

​             "group ads sort list page": true

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

​            "media file list page ": true

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

​            "update fixed point ads": true

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

​            "quantity ads list page": true

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

​             "vehicle group list": true

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

​          {

​            "add screen switch schedule task": true

​          },

​          {

​            "delete screen switch schedule task": true

​          },

​          {

​            "modify screen switch schedule task": true

​          },

​          {

​            "screen switch schedule task list page": true

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

​          },

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

​            "get updating details list": true

​          },

​           {

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

​          {

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

​          }

​        ]

​      }

​    },

​    "register_type": "email"

  },

  "error_code": 1001,

  "msg": "query success"

}
```

User update own information 

url:/v1/cms/user/updateCurrentUser

method:"put"

need token or not: Need

request parameters

Filed   type   instructions  required or not

nick_name    string    nickname  not required

response

```
{

  "error_code":1003,

  "msg":"update success"

}
```

Refresh token

url:/v1/cms/user/getToken

method:"get"

need token or not: Need

NOTES

The token must be refresh_token

When access_token lose efficiency , call this interface

When the interface return 41, will force to jump to login page

If return 200, need cache and send new access_token、refresh_token

response

```
{

  "error_code":1102 ,  //error code，int type

  "msg":"get token success",

  "data":{

​    "access_token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...."  //authenticated token, contains user groupId，valid from 2 hours to one day, decided by the settings

​    "refresh_token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"   //for refresh access_token, valid from one day to 7 days, decided by settings

  },

}
```

Download vehicle access certificate 

url:"/v1/cms/user/downLoadTaxiCertificate"

method:"get"

need token or not: Need  take certificate as query parameters :auth_token=""

Download success and return file 

Reset password by email

url:/v1/cms/user/resetPassword

method:"post"

need token or not: NO

Request body parameters

Filed   type   instructions  required or not

email    string    email address，required，must be legal email address  required

lng  string    language used by current user，zh or En    not required，En if not filled

Success and return data

```
{

  "error_code": 1105,

  "msg": "send mail success,please check your mail box"

}
```

Send register verification code

url :"/v1/cms/user/sendRegisterSmsCode"

mehtod:"post"

need token or not: NO

Request body parameters

```
{

  "mobile":"+8618451330795"

}


```

Send success and service side return data

```
{

  error_code :1107,

  "msg":"xxxxxx"

}
```

Mobile phone number register

url :"/v1/cms/user/registerByMobile"

method:"post"

Need token or not : No need

Request body parameters

```
{

  "mobile":"+8618451330795", //complete mobile phone number

  "code":"xxxx",

  "username":"18451330795" //phone number without country code

}
```

Register success and server side return data

// success response

```
{

  "error_code":1100 ,  //error code，int type

  "msg":"register success",

  "data":{

​    "access_token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9....",  //authenticated token, contains user groupId，valid from 2 hours to one day, decided by the settings

​    "refresh_token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"   //for refresh access_token, valid from one day to 7 days, decided by settings

  },

 "user_scope":"admin_scope", //root_scope super admin admin_scope admin common_scope sub user

}
```

//simple explanation: dual token design, for web side, when access_token lose efficiency, use refresh_token to refresh those two token, benefits of this method

//1.page no refresh get token

//2. if develop mobile app or applet etc, if user token expired, then force log out will create bad experience. 