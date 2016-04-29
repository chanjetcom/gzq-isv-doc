### Native接口列表
**接口文档说明：**
+ 如无特殊说明，系统类接口调用方向native -> js
+ 如无特殊说明，业务类接口调用方向js -> native

**业务列接口通用返回格式**
+ 返回格式为json
+ 通用格式说明：

|参数|说明|
|:-------------|:-------------|
|code|接口错误码|
|msg|错误提示信息|
|data|接口业务数据，由各个接口确定|
示例：

    {
        code:    //errorcode错误码
        msg:     //错误提示信息
        data:
        {
            type: “photo”,    //拍照回调类型
            nativeUrl: “”       //native本地图片路径
        }
    }
    
    
**接口列表**
    **系统类参数(Android端)**
    1.[onResume事件(resume)](./)
    2.[onPause事件(pause)](./)
    3.[KeyEvent.KEYCODE_BACK(backbutton)](./)
    4.[KeyEvent.KEYCODE_MENU(menubutton)](./)
    5.[KeyEvent.KEYCODE_SEARCH(searchbutton)](./)
    6.[KeyEvent.KEYCODE_VOLUME_UP(volumeupbutton)](./)
    7.[KeyEvent.KEYCODE_VOLUME_DOWN(volumedownbutton)](./)
    **系统类参数(iOS端)**
    8.[应用回到前台(resume)](./)
    9.[应用挂到后台(suspend)](./)
    **业务类参数**
    10.
    