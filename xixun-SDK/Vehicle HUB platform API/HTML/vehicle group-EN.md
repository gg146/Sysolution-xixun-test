>

# vehicle group interfaces

Instructions 

vehicle group modem interfaces

Catalogue 

1.1add a vehicle group

1.2delete a vehicle group

1.3update a vehicle group

1.4 get vehicle group list 

1.5 get vehicle group details

1.6delete one or more vehicles from the group

1.7add one or more vehicles to the specify group

Add a vehicle group

url:/v1/cms/taxiGroup/add

method:post

Need token or not: need

request body data

Character segment type  instructions  notes 

group_name  string         group name

icon_url  string     group icon address    

 response data

```
{

  error_code:1002,

  msg:"add success"

}
```

Delete a vehicle group

url:/v1/cms/taxiGroup/:id/delete

method:delete

Need token or not: need

Response data

```
{

  error_code:1004,

  msg:"delete success"

}
```

Update a vehicle group

url:/v1/cms/taxiGroup/:id/update

method:put

Need token or not: need

Response data 

Character segment  type  instructions notes

group_name  string         group name

icon_url  string        group icon address 

Response data

```
{

   error_code:1003,

  msg:"update success"

}
```

Get vehicle group list 

url:/v1/cms/taxiGroup/list

mehtod:get

Need token or not: need

Supported query parameters

Character segment  type  instructions 

page int  default is 1 if not filled

pageSize int   default is 10 if not filled

Response data

```
{

  "data": [

​    {

​      "id": "5f902152a514082ea4f251ad",

​      "name": "taxi",

​      "type": 0,

​      "is_default": false,

​      "icon_url": "",

​      "date_created": "2020-10-21T19:53:54.417+08:00",

​      "online_taxi_number": 0,

​      "total_taxi_number": 0,

​      "taxi_list": []

​    },

​    {

​      "id": "5f97ce99a51408329857113e",

​      "name": "bus",

​      "type": 0,

​      "is_default": false,

​      "icon_url": "",

​      "date_created": "2020-10-27T15:39:05.54+08:00",

​      "online_taxi_number": 0,

​      "total_taxi_number": 2,

​      "taxi_list": [

​        {

​          "id": "e26-420-40719",

​          "card_id": "e26-420-40719",

​          "name": "4444444444444444444444",

​          "group_id": "5f97ce99a51408329857113e",

​          "driver_tel": "333333333333333333333",

​          "taxi_photo_url": "",

​          "driver_name": "2222222222222222",

​          "licence": "111111111111111",

​          "imsi": "",

​          "iccid": "",

​          "card_detail": {

​            "online": false,

​            "width": 128,

​            "height": 64,

​            "brightness": 101,

​            "diskSize": 0,

​            "connVersion": "10.4.0-for-all",

​            "connVersionCode": 140,

​            "playerVersion": "unknown",

​            "playerVersionCode": -1,

​            "ledsetVersion": "5.2.5.3-2",

​            "ledsetVersionCode": 648,

​            "updateVersion": "7.3",

​            "updateVersionCode": 20,

​            "alias": "noname",

​            "netType": "WIFI",

​            "screenStatus": "on",

​            "birSessin": "",

​            "currentProgramId": "",

​            "currentProgramName": "unknown",

​            "volume": 8,

​            "locked": false,

​            "asu": 99,

​            "rssi": -35,

​            "temperature": 31,

​            "humidity": -1,

​            "transferred": false,

​            "sim": {

​              "deviceId": "863410048174921",

​              "networkCountryIso": "",

​              "number": "",

​              "simCountryIso": "",

​              "simOperatorName": "",

​              "simSerialNumber": "",

​              "simState": 1,

​              "subscriberId": ""

​            },

​            "monitoringUrl": "",

​            "taxiAppVersion": "3.0.16",

​            "taxiAppVersionCode": 24,

​            "basicAppVersion": "1.4.5.5",

​            "basicAppVersionCode": 16,

​            "starterVersion": "starter190",

​            "starterVersionCode": 190

​          },

​          "active_at": "0001-01-01T00:00:00Z"

​        },

​        {

​          "id": "e26-420-40720",

​          "card_id": "e26-420-40720",

​          "name": "4444444444444444444444",

​          "group_id": "5f97ce99a51408329857113e",

​          "driver_tel": "333333333333333333333",

​          "taxi_photo_url": "",

​          "driver_name": "2222222222222222",

​          "licence": "111111111111111",

​          "imsi": "",

​          "iccid": "",

​          "card_detail": {

​            "online": false,

​            "width": 540,

​            "height": 960,

​            "brightness": 101,

​            "diskSize": 0,

​            "connVersion": "10.4.0-for-all",

​            "connVersionCode": 140,

​            "playerVersion": "unknown",

​             "playerVersionCode": -1,

​            "ledsetVersion": "5.2.5.3-2",

​            "ledsetVersionCode": 648,

​            "updateVersion": "7.3",

​            "updateVersionCode": 20,

​             "alias": "noname",

​            "netType": "WIFI",

​            "screenStatus": "on",

​            "birSessin": "",

​            "currentProgramId": "",

​            "currentProgramName": "unknown",

​            "volume": 8,

​            "locked": false,

​            "asu": 99,

​            "rssi": -61,

​            "temperature": 32,

​            "humidity": -1,

​            "transferred": false,

​            "sim": {

​              "deviceId": "86341004819186",

​              "networkCountryIso": "cn",

​              "number": "",

​              "simCountryIso": "",

​              "simOperatorName": "",

​              "simSerialNumber": "",

​              "simState": 1,

​              "subscriberId": ""

​            },

​            "monitoringUrl": "",

​            "taxiAppVersion": "3.0.16",

​            "taxiAppVersionCode": 24,

​            "basicAppVersion": "1.4.5.5",

​            "basicAppVersionCode": 16,

​            "starterVersion": "starter190",

​            "starterVersionCode": 190

​          },

​          "active_at": "2020-11-13T10:29:24.222+08:00"

​        }

​      ]

​    },

​    {

​      "id": "5fb36c55a514082fc8f0c7e0",

​      "name": "721",

​      "type": 0,

​      "is_default": false,

​      "icon_url": "",

​      "date_created": "2020-11-17T14:23:17.683+08:00",

​      "online_taxi_number": 0,

​      "total_taxi_number": 1,

​      "taxi_list": [

​        {

​          "id": "e26-420-40721",

​          "card_id": "e26-420-40721",

​          "name": "no.123",

​          "group_id": "5fb36c55a514082fc8f0c7e0",

​          "driver_tel": "1234567890123456",

​          "taxi_photo_url": "",

​          "driver_name": "test 111",

​          "licence": "TEST123",

​          "imsi": "",

​          "iccid": "",

​          "card_detail": {

​            "online": true,

​            "width": 128,

​            "height": 64,

​            "brightness": 101,

​            "diskSize": 0,

​            "connVersion": "10.4.0-for-all",

​            "connVersionCode": 140,

​            "playerVersion": "unknown",

​            "playerVersionCode": -1,

​            "ledsetVersion": "5.2.5.6-7",

​            "ledsetVersionCode": 692,

​            "updateVersion": "7.3",

​            "updateVersionCode": 20,

​            "alias": "noname",

​            "netType": "WIFI",

​            "screenStatus": "on",

​            "birSessin": "",

​            "currentProgramId": "",

​            "currentProgramName": "unknown",

​            "volume": 4,

​            "locked": false,

​            "asu": 99,

​            "rssi": -39,

​            "temperature": 32,

​            "humidity": -1,

​            "transferred": false,

​            "sim": {

​              "deviceId": "863410048179342",

​              "networkCountryIso": "",

​              "number": "",

​              "simCountryIso": "",

​              "simOperatorName": "",

​              "simSerialNumber": "",

​               "simState": 1,

​              "subscriberId": ""

​            },

​            "monitoringUrl": "",

​            "taxiAppVersion": "3.1.0",

​            "taxiAppVersionCode": 30,

​            "basicAppVersion": "1.4.5.5",

​            "basicAppVersionCode": 16,

​            "starterVersion": "starter190",

​            "starterVersionCode": 190

​          },

​          "active_at": "2020-11-13T10:29:21.864+08:00"

​        }

​      ]

​    }

  ],

  "error_code": 1000,

  "msg": "get data success",

  "totalCount": 3

}
```

Get vehicle group details 

url:/v1/cms/taxiGroup/:id/detail

method:"get"

Need token or not: need

Return data

```
{

  "data": {

​    "id": "5f23c018a51408243c1d05e6",

​    "name": "test1111",

​    "type": 0,

​    "occupied": true,

​    "is_default": false,

​    "icon_url": "",

​    "date_created": "2020-07-31T14:54:16.208+08:00",

​    "online_taxi_number": 0,

​    "total_taxi_number": 2,

​    "taxi_list": [

​      {

​        "card_id": "e30-112-40018",

​        "name": "",

​        "group_id": "5f23c018a51408243c1d05e6",

​        "driver_tel": "",

​        "taxi_photo_url": "",

​        "driver_name": "",

​        "licence": "",

​        "imsi": "",

​        "iccid": ""

​      },

​      {

​        "card_id": "e30-112-49999",

​        "name": "car for testing",

​        "group_id": "5f23c018a51408243c1d05e6",

​        "driver_tel": "",

​        "taxi_photo_url": "",

​        "driver_name": "",

​        "licence": "",

​        "imsi": "",

​        "iccid": ""

​      }

​    ]

  },

  "error_code": 1001,

  "msg": "get data success"

}
```

Delete one or more vehicles from the group

url:"/v1/cms/taxiGroup/:id/removeTaxis"

method:"put"

Need token or not: need

Request body data 

Character segment  type  instructions  notes 

taxi_id_list  string  type’s data group   vehicle id that need to be removed  there is at least one item in data group 

Return data: return to new vehicle group details after removed, just like above, return data of get vehicle group details 

Add one or more vehicles in the specify group

url:"/v1/cms/taxiGroup/:id/addTaxis"

method:"put

Need token or not: need

Request body data

Character segment  type  instructions  notes

taxi_id_list  string type’s data group  vehicle id that need to be added  there is at least one item in the data group

Return data: return to new vehicle group details after added, just like above, the return data of get vehicle group details 