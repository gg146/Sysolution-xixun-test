set background 

Premise: controller adopts websocket to communicating once enter the platform system

Server sending data

```
{

  "type":"place_group_ad",

  "task":{

​    "id":"5e673567908de9e019fbf230",

​    "media_id":"5e802fad8ef9d7a431ed9b14",

​    "task_id":"5e89bdf18283968413a4503e",

​    "background_type":""  //background type

  }

}
```

//background_type support types in below

  "route", //route

  "brake", //brake

  "turn_left",//turn left

  "turn_right",//turn right

  "vacant", //vacant

  "hired",//hired

  "no_service", //no service

  "booked", //booked

  "logo", //logo



Device return data

```
{

  "type":"set_taxi_background", //

  "task_id":"5e89bdf18283968413a4503e",

  "id":"5e673567908de9e019fbf230"

}
```

Switch link address

premise：controller adopts websocket to communicating once enter the platform system

Server sending data

```
{

  "type":"switch_taxi_account",

  "task":{

​    "id":"5e673567908de9e019fbf230",

​    "task_id":"5e89bdf18283968413a4503e",

​    "account_id_token":"xxxx", //issued token 

​    "taxiServerURL":"http://xxxx", //server address

​    "taxiServerTLSURL":"https://xxxx" //server address

  }

}
```

Device return data

```
{

  "type":"switch_taxi_account",

   "id":"5e673567908de9e019fbf230",

  "task_id":"5e89bdf18283968413a4503e",

}
```

The server sending command of disconnecting device after receiving the return data from the device 

```
{

  "type":"time_to_disconnect",

  "task":{

​    "id":"5e673567908de9e019fbf230",

​    "task_id":"5e89bdf18283968413a4503e",

​    "account_id_token":"xxxx",

​    "taxiServerURL":"http://xxxx"

  }

}
```

Query ads sort 

premise：controller adopts websocket to communicating once enter the platform system

Server sending data

```
{

  "type":"get_advertise_order",

  "task":{

​    "id":"xxxxxx",

​    "task_id":"xxxxxxx"

  }

}
```

Device return data

```
{

 "type":"get_advertise_order",

  "task_id":"5e89bdf18283968413a4503e",

  "id":"5e673567908de9e019fbf230",

  "advertise_order":["xxxxx","xxxxx","xxxxxx"]    //string type array, it is each item is ads 

}
```

Query device ads

premise：controller adopts websocket to communicating once enter the platform system

Server sending data

```
{

  "type":"get_ad_list",

  "task":{

​    "id":"xxxxxx",

​    "task_id":"xxxxxxx"

  }

}
```

Device return data

```
{

 "type":"get_ad_list",

  "task_id":"5e89bdf18283968413a4503e",

  "id":"5e673567908de9e019fbf230",

"ad_list":  ["5e673567908de9e019fbf230","5e673567908de9e019fbf230"],//all ads list content

  "current_play_list":["5e673567908de9e019fbf230"]

 //List of currently playing advertising content

}
```

Switch of report play log 

premise：controller adopts websocket to communicating once enter the platform system

Json data format

// switch of report play log 

```
{

  "type":"update_player_log_switch",

  "task":{

​    "id":"5e89bdf18283968413a4503e",

​    "task_id":"5e89bdf18283968413a4503e",

​    "turn_on":true   //true open  false close  }

}
```

//return data 

```
{

  "type":"update_player_log_switch",

  "task_id":"5e89bdf18283968413a4503e",

  "id":"5e89bdf18283968413a4503e"

}
```

// switch of report GPS log

```
{

  "type":"update_gps_log_switch",

  "task":{

​    "id":"5e89bdf18283968413a4503e",

​    "task_id":"5e89bdf18283968413a4503e",

​    "turn_on":true   //true open  false close

  }

}
```

//return data

```
{

  "type":"update_gps_log_switch",

  "task_id":"5e89bdf18283968413a4503e",

  "id":"5e89bdf18283968413a4503e"

}
```

