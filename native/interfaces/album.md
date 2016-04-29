### 选图（选图-自动上传到工作圈资源服务器）
**接口名：Album**

**方法名：selectImgs**

**参数：**

|参数名称|	数据类型|	限定|	说明|
|:-------------|:-------------|:-------------|:-------------|
|selectedCount|Integer|非必填|已经选择的张数|
|maxCount|Integer|必填|选择张数的上限|

**示例：**
    `
    cordova.exec(
    success,    //<callback> success(<json>); 见下面第2)部分详述
    error,       //<callback> error(<json>); 见下面第2)部分详述
    ‘Album’,    //类名
    ‘selectImgs’,    //方法名
    [{
        “selectedCount”: “0”,    //已选的数量
        “maxCount”: “0”        //总数
    }]
    );
    `

**返回值:**

公共字段
|参数名|说明
|:-------------|:-------------|
|code	|错误码，成功为0|
|msg	|错误提示信息|

data节字段

|参数名称|	数据类型|	说明|
|:-------------|:-------------|:-------------|
|type|String|固定“select”|
|nativeUrls|jsonarray|选择的本地图片路径|


