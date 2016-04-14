## ISV使用工作圈IM发送消息接口说明
+ 功能说明：根据ISV的需要发送对应工作的消息

**公共参数:**
+ 接口的域名为 http://integzq.chanjet.com/notify/xxx
+ 公共参数 说明： 公共参数需要传递到get或post里面，get请求参数都传到参数中，post请求参数都传到form中。

### 接口信息
|接口调用方式 |	Restful Service|
|:-------------|:-------------|
|功能	     | 根据ISV的参数发送对应的工作消息|
|接口名称	|/web/openim/push|
|请求方法	|POST|
|接口类型	|用户授权接口|

### 接口公共参数
|参数名	|是否必填	|说明
|:-------------|:-------------|:-------------|
|sign	|必填	|接口的方法签名，有ISV分配到的FROM，ISV的APPsecret，消息的creatTime以及消息的alert等参数，组成的字符串，MD5生成|

### 消息模板参数

|参数名称|	数据类型|	限定|	说明|
|:-------------|:-------------|:-------------|:-------------|
|from	|String |必填	|ISV分配到的FROM|
|to	|String |必填	|消息接收人的UserID|
|appId	|String |必填	|ISV分配到的标识|
|orgId	|String |必填	|消息接收人所在的企业ID|
|alert	|String |必填	|消息的摘要|
|appName	|String |非必填	|ISV的名称|
|orgname	|String |非必填	|消息接收人所在企业的名称|
|userid	|String |非必填	|消息发送人的UserID|
|mtitle	|String |非必填	|消息的主标题|
|stitle	|String |非必填	|消息的副标题|
|quote	|String |非必填	|消息的引用|
|resId	|String |非必填	|消息附带的资源的标识|
|ext	|String |非必填	|消息的扩展信息|



### 接口返回值
+ 返回值数据类型：json
+ 返回值说明：

**返回值**
```
{
	"result":true,
	"err_code":0,
	"err_msg":""
}
```


### 业务错误信息提示码说明
|错误信息提示码|描述信息|
|:-------------|:-------------|
|60001|参数校验错误|
|60002|消息的接收人不在所给的企业中|
|61219|From每分钟中发送消息超出限制|
|61220|方法签名不正确|
|60582	|push服务错误|