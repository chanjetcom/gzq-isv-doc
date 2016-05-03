### 换取auth_code
**接口名：CspAuthCode**

**方法名：getCspAuthCode**

**参数：**

无

**示例：**
    `
    cordova.exec(
    success,    //<callback> success(<json>); 见下面第2)部分详述
    error,       //<callback> error(<json>); 见下面第2)部分详述
    ‘CspAuthCode’,    //类名
    ‘getCspAuthCode’,		//方法名
    [{
            “isSecure”: 0		//1，安全；0，非安全；默认为0。int型。
    }]
    );

    `

**返回值:**

公共字段

|参数名称|	说明|
|:-------------|:-------------|
|code	|错误码，成功为0|
|msg	|错误提示信息|


data节字段

|参数名称|	数据类型|	说明|
|:-------------|:-------------|:-------------|
|auth_code|String|当isSecure为0或1时，生效。用于单点登录|
|authCodeRelRandomKey|jsonarray|当isSecure为1时，生效|