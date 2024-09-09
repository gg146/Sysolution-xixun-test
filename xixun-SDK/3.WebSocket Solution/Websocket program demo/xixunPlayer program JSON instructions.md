# WebSocket Solution Program Demo

### 1. Instructions of sending program

```
{
  "preDownloadURL":"http://www.ledaips.com/file/download?id=",//Material link, used to concatenate the IDs in the source to form a complete link for device download of materials. Alternatively, this parameter can be omitted and a URL field can be added to the source to fill in the complete material download link. Please refer to the example section below
  "_type":"PlayXixunTask",//Fixed string, cannot be changed
  "id":"56623f42-54f1-49fd-8f7f-12b10193522a",//The device will save the program's unique ID value to the device, which can be assigned a random string
  "notificationURL":"http://192.168.2.11:8082/getJSON",//Post function address, used to receive program download progress
  "sendTo":"yzd-player",//Fixed string, cannot be changed
  "task":{
    "name":"测试",//Total program name
    "_id":"bf58063d-e850-45fa-bc9c-41da267e18c4",//Verify command ID, can be assigned a random string
    "insert":false,//Is it an insert program
    "items":[{
        "_id":"71513064",//Verify command ID, can be assigned a random string
        "_program":{
          "totalSize":489496,//The total byte size of all materials in this program must be accurate and error free
          "name":"图片2",//program name
          "width":64,//program width
          "layers":[
            {
              "sources":[
                {
                  "_type":"Image",//Image material type
                  "md5":"727cd88738b",//Material md5 value, obtain the unique md5 checksum value of the file stream
                  "name":"1",//material name
                  "mime":"image/jpeg",
                  "size":489496,//The byte size of the material must be accurate and error free
                  "fileExt":".jpg",//Material suffix
                  "url":"",//maerial path
                  "id":"609cfe5",//Material ID, the material will be named after this ID and saved to the internal storage of the device
                  "playTime":0,//The start playback time of the material on the timeline is set to 0 for the first image, which is equal to the playTime+timeSpan value of the previous material in the slideshow.
                  "timeSpan":10,//The playback duration of the material on the timeline, in seconds
                  "left":0,//The material in the program and the left margin
                  "top":0,//The margin at the top
                  "width":64,//material width
                  "height":64//material height
                }
              ],
              "repeat":false//Normal assignment of false is sufficient
            }
          ],
          "_id":"8d951790-93d2-46b1-b9c7-4d1a07bb2976",//Verify command ID, can be assigned a random string
          "height":64//program height
        },
        "repeatTimes":1,//The number of times the program is played when it is an insert program and there is no timing parameter	
        "schedules":[    //Timing field, refer to the timing parameter description below
               {
              "filterType":"None",		//necessary
              "timeType":"Range",		//necessary
              "startTime":"00:00",
              "endTime":"23:59",
              "dateType":"All"			//necessary
            }    
        ]
  }
}
```

###  1.1 schedule parameters instructions

```
dateType:(All:Unrestricted date,Range:Limited Date)
"startDate":"2019-03-03" //Scheduled start date
"endDate":"2019-03-26"	 //Scheduled end date

timeType:(All:Unrestricted time,Range:Limited time)
"startTime":"00:00",	//Scheduled start time
"endTime":"23:59",		//Scheduled start timr

filterType:(None:unrestricted weekday，Week:limited weekday)
 "weekFilter":[0，1，2，3，4，5，6 ],	//Sunday is 0,Monday is 1, and so on
```

### 2. Clear up program and other data from led controller

Function description: After calling this interface, all programs and downloaded program files in the control card will be completely deleted, and the player will display the default logo image.
Sending data:

```
{
	"cardId": "y60-620-40490",
	"_type":"DeleteTask",
	"sendTo":"yzd-player"
}
```

return data

```
{
  	"_type": "DataCallback",
  	"result": "received command",
  	"commandId": "61234811c4c3c90c07326ebf",
  	"cardId": "y60-620-40490",
  	"_cardId": "y60-620-40490"
}
```

### 3. Demo of sending program

####  3.1 Image

```
{
  "preDownloadURL":"http://www.ledaips.com/file/download?id=",
  "_type":"PlayXixunTask",
  "sendTo":"yzd-player",
  "id":"56623f42-54f1-49fd-8f7f-12b10193522a",
  "notificationURL":"http://192.168.2.11:8082/getJSON",
  "task":{
    "name":"图片轮播",
    "_id":"bf58063d-e850-45fa-bc9c-41da267e18c4",
    "insert":false,
    "items":[{
        "_id":"71513064",
        "_program":{
          "totalSize":489496,
          "name":"图片2",
          "width":64,
          "layers":[
            {
              "sources":[
                {
                  "_type":"Image",
                  "md5":"727cd88738b",
                  "name":"1",
                  "mime":"image/jpeg",
                  "size":489496,
                  "fileExt":".jpg",
                  "url":"https://www.ledaips.com/file/download?id=64d300120c71c21d62cd0343",
                  "id":"609cfe5",
                  "playTime":0,
                  "timeSpan":10,
                  "left":0,
                  "top":0,
                  "width":64,
                  "height":64
                }
              ],
              "repeat":false
            }
          ],
          "_id":"8d951790-93d2-46b1-b9c7-4d1a07bb2976",
          "height":64
        },
        "repeatTimes":1,
        "schedules":[]
  }
}
```

#### 3.2 Video

```
{
			"preDownloadURL":"http://www.ledaips.com/file/download?id=",
            "_type": "PlayXixunTask",
			"sendTo": "yzd-player", 
            "id": "600a297fa480eb3121a02823",
            "notificationURL":"http://192.168.2.12:8083/getJSON",
            "task": {
                "name": "测试",
                "_id": "6007d65eb4ce829b1fef28f4",
                "insert":false,
                "items": [
                    {
                        "_id": "9146b44e-7fe4-4098-b858-f2499b88d0ac",
                        "_program": {
                            "totalSize": 2040197,
                            "name": "测试",
                            "width": 64,
                            "layers": [
                                {
                                    "sources": [
                                        {
                                            "entryEffectTimeSpan": 0,
                                            "_type": "Video",
                                            "exitEffect": "None",
                                            "entryEffect": "None",
                                            "top": 0,
                                            "size": 2040197,
                                            "left": 0,
											"url":"http://192.168.1.142:8081/3.mp4",
                                            "name": "600a297fa480eb3121a02823.mp4",
                                            "width": 64,
											"fileExt": ".mp4",
											"mime": "video/mp4",
                                            "playTime": 0,
                                            "timeSpan": 31,
                                            "lineHeight": 0,
                                            "id": "600a297fa480eb3121a02823",
                                            "exitEffectTimeSpan": 0,
                                            "height": 64,
                                            "md5": "2e7e39eaa3faa90f5d5b34536722ce49"
                                        }
                                    ],
                                    "repeat": false
                                }
                            ],
                            "_id": "600a297fa480eb3121a02823",
                            "height": 64
                        },
						"repeatTimes": 1,
                       "schedules":[]
                    }
                ]
            }
        }
```

#### 3.3 GIF animation

```
{
  "preDownloadURL":"http://www.ledaips.com/file/download?id=",
  "_type":"PlayXixunTask",
  "sendTo":"yzd-player",
  "id":"56623f42-54f1-49fd-8f7f-12b10193522a",
  "notificationURL":"http://192.168.2.11:8082/getJSON",
  "task":{
    "name":"gif动图",
    "_id":"bf58063d-e850-45fa-bc9c-41da267e18c4",
    "insert":true,
    "items":[
      {
        "_id":"71513064-1e6c-4a3d-87cc-2fc29a00e78e",
        "_program":{
          "totalSize":522377,
          "name":"gif动图",
          "width":128,
          "layers":[
            {
              "sources":[
                {
                  "_type":"Image",
                  "md5":"9baaee1424433cb810463d195c6d990d",
                  "name":"c71c9a111f3d11c08d5bd00cbc29aef0.gif",
                  "mime":"image/gif",
                  "size":522377,
                  "fileExt":".gif",
                  "id":"60b61f8d52f237932b4a2fec",
                  "url":"",
                  "playTime":0,
                  "timeSpan":9,
                  "left":0,
                  "top":0,
                  "width":128,
                  "height":256
                }
              ],
              "repeat":false
            }
          ],
          "_id":"8d951790-93d2-46b1-b9c7-4d1a07bb2976",
          "height":256
        },
        "repeatTimes":1,
        "schedules":[
          
        ]
      }
    ]
  }
}
```

#### 3.4 single line text

```
{
  "preDownloadURL":"http://www.ledaips.com/file/download?id=",
  "_type":"PlayXixunTask",
  "sendTo":"yzd-player",
  "id":"56623f42-54f1-49fd-8f7f-12b10193522a",
  "notificationURL":"http://192.168.2.11:8082/getJSON",
  "task":{
    "name":"单行文本",
    "_id":"bf58063d-e850-45fa-bc9c-41da267e18c4",
    "insert":true,
    "items":[
      {
        "_id":"71513064-1e6c-4a3d-87cc-2fc29a00e78e",
        "_program":{
          "totalSize":0,
          "name":"单行文本",
          "width":128,
          "layers":[
            {
              "sources":[
                {
                  "id":"",
                  "name":"SingleText",
                  "_type":"SingleLineText",
                  "lineHeight":1.4,
                  "speed":20,
                  "html":"<span style=\"font-size:14px;color:#0000FF;\">Please write something...</span>",
                  "playTime":0,
                  "timeSpan":10,
                  "left":0,
                  "top":0,
                  "width":128,
                  "height":256
                }
              ],
              "repeat":false
            }
          ],
          "_id":"8d951790-93d2-46b1-b9c7-4d1a07bb2976",
          "height":256
        },
        "repeatTimes":1,
        "schedules":[
          
        ]
      }
    ]
  }
}
```

#### Partial parameter description

```
_type:The material is of single line text type and must be SingleLineText, case sensitive
id: material id，Can be an empty string, can be set to a random value, and this field is indispensable
lineHeight: line height
speed:Text movement speed, indicating that the text moves from beginning to end within a specified time. The larger the value, the slower the speed, measured in seconds
html:Text content, in HTML format, can be edited with inline styles for text formatting, including background color, font size, font color, etc
```

#### 3.5 Multiline text

```
{
	"preDownloadURL": "http://www.ledaips.com/file/download?id=",
	"_type": "PlayXixunTask",
	"sendTo": "yzd-player",
	"id": "56623f42-54f1-49fd-8f7f-12b10193522a",
	"notificationURL": "http://192.168.2.11:8082/getJSON",
	"task": {
		"name": "多行文本",
		"_id": "bf58063d-e850-45fa-bc9c-41da267e18c4",
		"insert": true,
		"items": [{
			"_id": "71513064-1e6c-4a3d-87cc-2fc29a00e78e",
			"_program": {
				"_id": "64f928aee09465613d6f13cc",
				"totalSize": 0,
				"name": "多行文本",
				"width": 520,
				"height": 520,
				"layers": [{
					"repeat": false,
					"sources": [{
						"backgroundColor": "rgba(0,0,0,1)",
						"id": "",
						"name": "MultiText",
						"_type": "MultiLineText",
						"speed": 10,
						"lineHeight": 1.4,
						"center": false,
						"html": "<p><span style=\"color:#DD1144;font-size:10px, Courier, &quot;background-color:#FFFFFF;\">青春本就是马不停蹄的错过和相遇。在这路遥马急的人间，谁又能记住谁几年？</span></p>",
						"playTime": 0,
						"timeSpan": 100,
						"left": 0,
						"top": 0,
						"width": 520,
						"height": 520,
						"entryEffect": "None",
						"exitEffect": "None",
						"entryEffectTimeSpan": 0,
						"exitEffectTimeSpan": 0,
						"sUrl": "",
						"sInterval": 0
					}]
				}]
			}
		}]
	}
}
```

Partial parameter description

```
_type:The material is of multiline text type and must be MultiLineText, case sensitive
id:Material ID, can be an empty string, can be set to a random value, and this field is indispensable
lineHeight:line height
center:Is the text centered
html:Multi line text content, in HTML format, can be edited with inline styles to include background color, font size, font color, etc. Use</br>tags to wrap the text
```

#### 3.6 Digital Clock

```
{
  "preDownloadURL":"http://www.ledaips.com/file/download?id=",
  "_type":"PlayXixunTask",
  "sendTo":"yzd-player",
  "id":"56623f42-54f1-49fd-8f7f-12b10193522a",
  "notificationURL":"http://192.168.2.11:8082/getJSON",
  "task":{
    "name":"数字时钟",
    "_id":"bf58063d-e850-45fa-bc9c-41da267e18c4",
    "insert":true,
    "items":[
      {
        "_id":"71513064-1e6c-4a3d-87cc-2fc29a00e78e",
        "_program":{
          "totalSize":0,
          "name":"数字时钟",
          "width":128,
          "layers":[
            {
              "sources":[
                {
                  "id":"",
                  "name":"DigitalClock",
                  "_type":"DigitalClock",
                  "html":"<span><span style=\"font-size:9px;\">%yyear</span><span style=\"font-size:9px;\">%Mmonth%ddate&nbsp;<br />\n%w&nbsp; %am</span></span><span style=\"font-size:9px;\"></span><br />\n<span style=\"font-size:9px;\">%H:%m:%s&nbsp;</span>",
                  "lineHeight":1.4,
                  "timezone":8,
                  "language":"en",
                  "playTime":0,
                  "timeSpan":10,
                  "left":0,
                  "top":0,
                  "width":128,
                  "height":256,
                  "entryEffect":"None",
                  "exitEffect":"None",
                  "entryEffectTimeSpan":0,
                  "exitEffectTimeSpan":0
                }
              ],
              "repeat":false
            }
          ],
          "_id":"8d951790-93d2-46b1-b9c7-4d1a07bb2976",
          "height":256
        },
        "repeatTimes":1,
        "schedules":[
          
        ]
      }
    ]
  }
}
```

Partial parameter description

```
HTML: Content to be displayed, HTML format, placeholder meaning:% y: year,% M: month (numerical representation, note capitalization),% Mw: month (textual representation, note capitalization),% d: day,% w: week,% H: hour (24-hour format, note capitalization),% h: hour (12 hour format),% am: morning and afternoon,% m: minute,% s: second.
Timezone: Display the time zone corresponding to the time
Language: Language options include CN Chinese, EN English, PT BR Portuguese, FR French
```

#### 3.7 Analog clock

```
{
  "preDownloadURL":"http://www.ledaips.com/file/download?id=",
  "_type":"PlayXixunTask",
  "sendTo":"yzd-player",
  "id":"56623f42-54f1-49fd-8f7f-12b10193522a",
  "notificationURL":"http://192.168.2.11:8082/getJSON",
  "task":{
    "name":"模拟时钟",
    "_id":"bf58063d-e850-45fa-bc9c-41da267e18c4",
    "insert":true,
    "items":[
      {
        "_id":"71513064-1e6c-4a3d-87cc-2fc29a00e78e",
        "_program":{
          "totalSize":0,
          "name":"模拟时钟",
          "width":128,
          "layers":[
            {
              "sources":[
                {
                  "id":"60b624d152f237932b4a6392",
                  "name":"时间",
                  "_type":"AnalogClock",
                  "shade":0,
                  "opacity":1,
                  "showBg":true,
                  "bgColor":"#ffffff",
                  "showHourScale":true,
                  "scaleHourColor":"#12229c",
                  "showMinScale":true,
                  "scaleMinColor":"#3bc73b",
                  "scaleStyle":3,
                  "showScaleNum":true,
                  "pinStyle":1,
                  "pinHourColor":"#ff0000",
                  "pinMinColor":"#00ff00",
                  "pinSecColor":"#fbca00",
                  "showSecond":true,
                  "playTime":0,
                  "timeSpan":10,
                  "left":0,
                  "top":0,
                  "width":128,
                  "height":256
                }
              ],
              "repeat":false
            }
          ],
          "_id":"8d951790-93d2-46b1-b9c7-4d1a07bb2976",
          "height":256
        },
        "repeatTimes":1,
        "schedules":[
          
        ]
      }
    ]
  }
}
```

#### Partial parameter description

```
shade： default is 0
opacity：opaque
ShowBg: Display background or not
BgColor: Background color
ShowHourScale: Display the hour scale
ScaleHourColor: hour scale color
ShowMinScale: Display minute scale
ScaleMinColor: minute scale color
ScaleStyle: There are four options for scale styles: integer 0~3. 0 line line (both integer and minute scales are short lines), 1 point line (integer points are points, minute scales are short lines), 2 lines point (integer points are represented by short lines, minute scales are represented by dots), 3 points point (both integer and minute scales are represented by dots)
ShowScaleNum: integer scale displays numbers
PinStyle: pointer style, integer 1-3 (1 represents diamond, 2 represents triangle, 3 represents rectangle)
PinHourColor: Clock pointer color
PinMinColor: Clock minute hand color
PinSecColor: Clock Second Hand Color
ShowSecond: Display the second hand or not
```

#### 3.8 URL

```
{
    "preDownloadURL": "http://www.ledaips.com/file/download?id=",
    "_type": "PlayXixunTask",
    "sendTo": "yzd-player",
    "id": "1799b913-d6c9-46ba-a885-70f14ac69bb3",
    "notificationURL": null,
    "task": {
        "name": "weburlTest",
        "_id": "8c59a1ab-3186-4138-bfb3-cab8fa7bc7f6",
        "insert": true,
        "items": [{
            "_id": "06821fa7-9fc8-46d3-9c99-566bbd84251f",
            "_program": {
                "totalSize": 0,
                "name": "weburlTest",
                "width": 128,
                "_id": "292c53ee-585e-4dac-9160-b9d2a2e302c8",
                "height": 256,
                "layers": [{
                    "repeat": false,
                    "sources": [{
                        "name": "webURL123",
                        "_type": "WebURL",
                        "url": "https://www.baidu.com",
                        "playTime": 0,
                        "timeSpan": 10,
                        "left": 0,
                        "top": 0,
                        "width": 128,
                        "height": 256
                    }]
                }]
            },
            "repeatTimes": 1,
            "schedules": []
        }]
    }
}
```

