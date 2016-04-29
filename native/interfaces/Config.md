### 配置信息
**接口名：Config**

**方法名：getConfig**

**参数：**
无

**示例：**
    `
    cordova.exec(
    success,    //<callback> success(<json>); 见下面第2)部分详述
    error,       //<callback> error(<json>); 见下面第2)部分详述
    ‘Config’,    //类名
    ‘getConfig’,    //方法名
    []
    );
    `

**返回值:**

公共字段

|参数名称|	说明|
|:-------------|:-------------|
|code	|错误码，成功为0|
|msg	|错误提示信息|


data节字段（冗余字段请忽略）

|参数名称|	数据类型|	说明|
|:-------------|:-------------|:-------------|
|entId|String|企业ID|
|appId|Integer|轻应用ID|
|userid|String|用户id|
|version|String|工作圈native的当前版本号，如1.1.5.001|
|deviceInfo|LightAppDeviceInfo|设备信息|
|ext|String|IM消息中的透传字段|
|entName|String|当前企业名|
|entAvatar|String|当前企业logo链接|
|userName|String|用户名|
|userAvatar|String|用户头像链接|
|platformExtension|String|轻应用在CIA平台的订购信息，透传字段|
|currentTimeStamp|Long|当前服务端时间戳|

LightAppDeviceInfo类型字段：

|参数名称|	数据类型|	说明|
|:-------------|:-------------|:-------------|
|manufacturer|String|制造商（厂商）|
|model|String|型号|
|osRelease|String|系统版本|
|networkStatus|String|网络状态：UNKNOWN,ETHERNET, WIFI,CELL_2G,CELL_3G,CELL_4G,CELL, NoNetwork|
|usedMemory|String|当前内存占用|
|availableMemory|String|最大可用内存|
|deviceId|String|给到服务端的deviceId|
|deviceType|String|表示设备类型：APH（Android）、IPH（iOS）|