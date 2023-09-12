# xixunPlayer program JSON instructions

### To explain necessary properties of video, image, Flash, single/mutil line text, digital clock, countdown and weather forecast materials supported by xixunplayer, please refer to following content:

```java

Recommend to retain the properties not explained in this document, please ignore the properties not quoted in this document. 
{
	//realtime interface command type，to note xixunplayer to display information, content is fixed,case sensitivity
    "type":"commandXixunPlayer",
	//command data
    "command":{
		//xixunplayer command type，to display program, content is fixed,case sensitivity        "_type":"PlayXixunTask",
		//id must has irrepeat content
        "id":"3be5e443-d025-4f8d-b708-62ac89c5b5fe", 
		//preDownloadURL property very important, xixunplayer will connect preDownloadURL and source id property in program through character string to constitute a valid //http download link. If preDownloadURL property not correct then can not download the image or video file. 

		//TIPS：if not use preDownloadURL+id as url to download file, then can add url property in source ofVideo、Image、Flash materials to specify the download path.
        "preDownloadURL":"https://m2mled.net/file/download?id=",
		//notificationURL property will be used to note customer server of program download process. If not set this property then customer will has no idea of download status. 
		//data format of download process, please refer to protocolC document
        "notificationURL":"",
		//program task data
        "task":{
			//_id must has irrepeat content
            "_id":"55f5b637-a529-4807-8063-deeb3c12f9ab",
			//program name
            "name":"demo",
			// belonging department, can be null or empty character string
            "_department":null,
			//a task contains more than one programs, each program corresponds one item, play rules sorted by time first, if time same then sort by priority property value from small to large (value small display first)
            "items":[
                {
					//_id must has irrepeat content
                    "_id":"0d10f114-b93d-4eb7-a1a7-60311eeab6b2",
					//program data
                    "_program":{
						//_id must has irrepeat content
                        "_id":"5c909eca4477c9247940613b",
						//cumulative sum of each material’s size property in current programs’ sources array
                        "totalSize":14545722,
						//program name
                        "name":"name",
						//program window width and height
                        "width":300,
                        "height":240,
						//company id，not important, can be randomly if not use AIPS platform
                        "_company":"alahover",
						//department id，not important, can be randomly if not use AIPS platform
                        "_department":"539eaaedb6e1232a1566d9c2",
						// role id，not important, can be randomly if not use AIPS platform

                        "_role":"539eaaedb6e1232a1566d9c3",
						//user，not important, can be randomly if not use AIPS platform
                        "_user":"yzd",
						//program version type,default 0, no need modify, will be modified by xixunplayer 
                        "__v":0,
						//layer is the time axis for program editing in AIPS platform, for play content in layers, can preview effect in AIPS platform
                        "layers":[
                            {
								//some repeat=true，sources of current layer will repeat play according to the longest layer, normally set false
                                "repeat":false,
								//material data
                                "sources":[
                                    {
										//video play duration, can ignore, xixunplayer not use this value
                                        "maxPlayTime":7,
										//material is video type, must be Video, case sensitivity 
                                        "_type":"Video",
										//video file content MD5 value                                        "md5":"eb2415b138b3c2a5984db4d57652f4c9",
										//video name
                                        "name":"iphone.MOV",
										//mp4 file, please use "video/mp4"
                                        "mime":"video/quicktime",
										//material file size, unit bytes
                                        "size":14237682,
										//6 properties in below can ignore, xixunplayer not use
                                        "enabled":true,
                                        "enabledBy":"check",
                                        "mediaGroup":null,
                                        "deletedBy":null,
                                        "deleted":null,
                                        "newName":null,
										//platform file store path, can be empty character string
                                        "oldFilePath":"/home/xixun/upload/alahover/20191/5c6f81b6d17fe59b436f5257",
										//file extension name, can be empty string
                                        "fileExt":".MOV",
										//material id，can not be empty, can not repeat with other id
                                        "id":"5c6f81b6d17fe59b436f5257",
										//start time in time axis , unit second
                                        "playTime":10,
										//play duration time, unit second
                                        "timeSpan":7,
										//top left coordinate of material, unit pixel
                                        "left":0,
                                        "top":0,
										//width and height of material, unit pixel
                                        "width":150,
                                        "height":120,
										//enter and exit effect, please refer to appendix1
                                        "entryEffect":"None",
                                        "exitEffect":"None",
										//duration of enter and exit effect, unit second
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0
                                    },
                                    {
										//material is image type, must be Image, case sensitivity
                                        "_type":"Image",
										//file content MD5 value
                                        "md5":"43103948f8bf4418e54819552cd18b5e",
										//material name
                                        "name":"1234.jpg",
										//GIF use"image/gif"
                                        "mime":"image/jpeg",
										//material file size, unit bytes
                                        "size":3370,
										//following properties same like that of Video
                                        "enabled":true,
                                        "enabledBy":"test1",
                                        "mediaGroup":null,
                                        "deletedBy":null,
                                        "deleted":null,
                                        "newName":null,
                                        "oldFilePath":"/home/xixun/upload/alahover/201811/5c122925a62960b53ca66dd9",
                                        "fileExt":".jpg",
                                        "id":"5c122925a62960b53ca66dd9",
                                        "playTime":0,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0
                                    },
                                    {
										//material id，can not be empty and can not repeat with other id 
                                        "id":"555d5adc1c0170327ff45b93",
                                        "name":"001",
										//material is analog clock, must be AnalogClock,case sensitivity 
                                        "_type":"AnalogClock",
										//__TODO to be determined
                                        "shade":0,
                                        "opacity":1,
                                        "showBg":true,
                                        "bgColor":"#482c51",
                                        "showHourScale":true,
                                        "scaleHourColor":"#12229c",
                                        "showMinScale":true,
                                        "scaleMinColor":"#3bc73b",
                                        "scaleStyle":3,
                                        "showScaleNum":true,
                                        "pinStyle":1,
                                        "pinHourColor":"#ff0000",
                                        "pinMinColor":"#00ffd2",
                                        "pinSecColor":"#fbca00",
                                        "showSecond":true,
										//following properties are the same with those ofVideo
                                        "playTime":17,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0
                                    },
                                    {
										//digital clock material id，can be empty, can set value
                                        "id":"",
                                        "name":"DigitalClock",
										//material is digital clock type, must be DigitalClock，case sensitivity
                                        "_type":"DigitalClock",
										//content needs to be playe，html format，
										//placeholder meanings：%y:year,%M:month(digital, case sensitivity),%Mw:month( text, case sensitivity),%d:day,%w:week,%H:hour(24 hour ,case sensitivity),%h:hour (12 hour),%am:morning time or afternoon time,%m:minute,%s:second,
                                        "html":"%w, %Mw %d %y<br />%h:%m:%s %am",
										//line height
                                        "lineHeight":1.4,
										//show the corresponding time zone of current time
                                        "timezone":8,
										//can choose cn，en，pt-BR，fr
                                        "language":"en",
										//following properties same with those of Video
                                        "playTime":27,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0
                                    },
                                    {
										//countdown material id，can be empty, can set value
                                        "id":"",
                                        "name":"Countdown",
										//material is countdown type, must be Countdown，case sensitivity
                                        "_type":"Countdown",
										//line height
                                        "lineHeight":1.4,
										//target time
                                        "time":"2014-5-1 10:30",
										//show information，html format，place holder meanings：%d:rest days,%h:rest hours,%m:rest minutes,%s:rest seconds
                                        "html":"Remain<br />%dDay%hHours%mMins%sSecs",
										//following properties same with those of Video
                                        "playTime":37,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0
                                    },
                                    {
										//single line material id，can be empty, can set value
                                        "id":"",
                                        "name":"SingleText",
										//material is single line text type, must be SingleLineText，case sensitivity
                                        "_type":"SingleLineText",
										//line height
                                        "lineHeight":1.4,
										//text move speed, means text move from begin to end in the specified time, value bigger, speed slower, unit second
                                        "speed":20,
										//text content，html format
                                        "html":"Please write something...",
										//following properties are the same with those ofVideo
                                        "playTime":47,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0
                                    },
                                    {
										//background color，a is transparent value
                                        "backgroundColor":"rgba(0,0,0,1)",
										//multi-line text material id，can be empty, can set value
                                        "id":"",
                                        "name":"MultiText",
										//material is multi-line text, must be MultiLineText，case sensitivity
                                        "_type":"MultiLineText",
										//turn the page waiting time，unit second
                                        "speed":10,
										//text line height
                                        "lineHeight":1.4,
										//text center or not
                                        "center":true,
										//multi-line content，html format
                                        "html":"<p>First Page：<br />temperature:%c℃(%f℉)</p>",
										//following properties are the same with those ofVideo
                                        "playTime":57,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0,
										//following two properties can ignore, xixunplayer not use
                                        "sUrl":"",
                                        "sInterval":0
                                    },
                                    {
										//sensor material id，can be empty, can set value
                                        "id":"",
                                        "name":"Sensor",
										//material is sensor data type, must be MultiLineText，case sensitivity
                                        "_type":"MultiLineText",
										//turn the page waiting time, unit second
                                        "speed":10,
										//text line height
                                        "lineHeight":1.4,
										//text center or not
                                        "center":true,
										//text content，html format
                                        "html":"<p>temperature:%c℃(%f℉)</p>",
										following properties are the same with those ofVideo
                                        "playTime":67,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0,
										//following two properties can ignore, xixunplayer not use
                                        "sUrl":"",
                                        "sInterval":0,
										//background color，a is transparent value
                                        "backgroundColor":"rgba(0, 0, 0, 0)"
                                    },
                                    {
										//material is Flash type，must be Flash，case sensitivity
                                        "_type":"Flash",
										//flash file content MD5 value
                                        "md5":"f8b875a75a9231c7f9632cd5ce3af485",
										//material name
                                        "name":"download.swf",
										//mime type，flash use this character string
                                        "mime":"application/x-shockwave-flash",
										//file size, unit bytes
                                        "size":304670,
										//following 6 properties can ignore,xixunplayer not use
                                        "enabled":true,
                                        "enabledBy":"yzd",
                                        "mediaGroup":null,
                                        "deletedBy":null,
                                        "deleted":null,
                                        "newName":null,
										//platform file store path, can be empty character string 
                                        "oldFilePath":"/home/xixun/upload/alahover/20165/57708d39342b5da0102f82c6",
										//file extension name, can not be empty, please set as flash extension name
                                        "fileExt":".swf",
										//id must be irrepeat content
                                        "id":"57708d39342b5da0102f82c6",
										//following properties are the same with those of Video
                                        "playTime":77,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0
                                    },
                                    {
										//weather forecast material id，can be empty, can set value
                                        "id":"",
                                        "name":"today",
										//material is weather forecast type, must be Weather，case sensitivity
                                        "_type":"Weather",
										//city name，support almost all cities in China
                                        "city":"Shanghai",
										//text line height
                                        "lineHeight":1,
										//show content，html format
										//%{current}:current temperature
										//%{aqi}:AQI（air quality index）
										//%{arr.0.date}:date（include realtime temperature）
										//%{arr.0.type}:weather condition of the day
										//%{arr.0.high}:maximum temperature of the day
										//%{arr.0.low}:Minimum temperature of the day

										//%{arr.0.fx}:wind direction of the day
										//%{arr.0.fl}:wind power of the day
										//%{arr.0.img-32-32}:weather condition image of the day，format：img-width-height(blue)，img2-width-height（gray）
										//all yesterday in { } in above means yesterday，arr.0 means today，1 means tomorrow，2 means the day after tomorrow，3 means three days from now，4 means 4 days from now
                                        "html":"today：%{arr.0.date}<br />realtime temperature：%{current}℃<br />air quality ：%{aqi}<br />%{arr.0.img-32-32}%{arr.0.type}<br />highest:%{arr.0.high}℃ lowest：%{arr.0.low}℃<br />%{arr.0.fx} %{arr.0.fl}",
										//following properties are the same with those ofVideo
                                        "playTime":87,
                                        "timeSpan":10,
                                        "left":0,
                                        "top":0,
                                        "width":150,
                                        "height":120,
                                        "entryEffect":"None",
                                        "exitEffect":"None",
                                        "entryEffectTimeSpan":0,
                                        "exitEffectTimeSpan":0,
										//city code，please refer to appendix 2
                                        "code":101020100
                                    }
                                ]
                            }
                        ],
						//create time, can be empty
                        "dateCreated":"2019-03-19T07:48:26.984Z"
                    },
					//task item priority，smaller value higher priority, multiple programs in the same play time section display by this priority
                    "priority":0,
					//play times after get right to display according to priority
                    "repeatTimes":1,
					//0 is advance program，2 is simple program					//simple program can only be  Video or Image，can not specify effect，default display coordinate 0，0，material width and height default to be same as program width and height.                    "version":0,
					//display in schedule time，date, time and week day can be setup in the same time, and logic relationship
                    "schedules":[
                {
					//All no specified date
                    "dateType":"All",
                    "startDate":null,
                    "endDate":null,
					//All no specified time
                    "timeType":"All",
                    "startTime":null,
                    "endTime":null,
					//specified work days，display at Monday, Tuesday and Wednesday
                    "filterType":"Week",
                    "weekFilter":[
                        1,
                        2,
                        3
                    ],
					//no specified month
                    "monthFilter":[

                    ],
					//language, can ignore
                    "lng":"zh-CN"
                },
                {
				//All no specified date
                    "dateType":"All",
                    "startDate":null,
                    "endDate":null,
					//specified time section, display during 00:00-23：59
                    "timeType":"Range",
                    "startTime":"00:00",
                    "endTime":"23:59",
					//no specified week day            
         "filterType":"None",
                    "weekFilter":[

                    ],
					//no specified month
                    "monthFilter":[

                    ],
                    "lng":"zh-CN"
                },
                {
				//specified display in month
                    "dateType":"Range",
                    "startDate":"2019-03-03",
                    "endDate":"2019-03-26",
                    "timeType":"All",
                    "startTime":null,
                    "endTime":null,
                    "filterType":"None",
                    "weekFilter":[

                    ],
                    "monthFilter":[

                    ],
                    "lng":"zh-CN"
                }
            ]
                }
            ],
			//can specified download program date and time , recommend to set null
            "executeDate":null,
			//command id，recommend to set valid character string, not repeat with other id
            "cmdId":"55f5b637-a529-4807-8063-deeb3c12f9ab"
        }
    }
}



Appendix 1：effects type：fade out and zoom out can not be as enter in effects, fade in and zoom in cannot be as exit effects.
	None,		
	ALPHA_IN,					//fade in 
	ALPHA_OUT,					//fade out
	MOVING_LEFT,				//continue moving left
	MOVING_RIGHT,				//continue moving right
	MOVING_TOP,					//continue moving up
	MOVING_BOTTOM,				//continue moving bottom
	ZOOM_IN,					//zoom in
	ZOOM_OUT,					//zoom out
	ZOOM_IN_LEFT_BOTTOM,		//zoom in left bottom
	ZOOM_IN_LEFT_TOP,			//zoom in left top
	ZOOM_IN_RIGHT_TOP,			//zoom in right top
	ZOOM_IN_RIGHT_BOTTOM,		//zoom in right bottom
	ZOOM_OUT_LEFT_BOTTOM,		//zoom out left bottom
	ZOOM_OUT_LEFT_TOP,			//zoom out left top
	ZOOM_OUT_RIGHT_TOP,			//zoom out right top
	ZOOM_OUT_RIGHT_BOTTOM,		//zoom out right bottom
	ROTATE_RIGHT,				//rotate right
	ROTATE_LEFT					//rotate left
```

