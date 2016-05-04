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
```
    {
        code:    //errorcode错误码
        msg:     //错误提示信息
        data:
        {
            type: “photo”,    //拍照回调类型
            nativeUrl: “”       //native本地图片路径
        }
    }
```
    
    
#### 接口列表

**系统类接口**

1. [deviceready](systemEvent.md)
2. [onResume事件](systemEvent.md)
3. [onPause事件](systemEvent.md)
4. [键盘事件KeyEvent.KEYCODE_BACK](systemEvent.md)
5. [键盘事件KeyEvent.KEYCODE_MENU](systemEvent.md)
6. [键盘事件KeyEvent.KEYCODE_SEARCH](systemEvent.md)
7. [键盘事件KeyEvent.KEYCODE_VOLUME_UP](systemEvent.md)
8. [键盘事件KeyEvent.KEYCODE_VOLUME_DOWN](systemEvent.md)

**业务类接口**

9. [选图（选图-自动上传到工作圈资源服务器）](interfaces/Album.md)

**Cordova原生插件扩展**

10. [Cordova原生插件扩展](cordovaOrigin.md)