### 基本接入方式
**第一步申请ISV账号及创建轻应用app（暂不需要）**
[详见ISV接入指南](./native/ISVGuide.md)

**第二步如果需要native接口，请添加cordova.js**
[下载](./native/downloadCordova.md)

**第三步根据需要调用native接口**
[接口列表](./native/nativeInterfaceList.md)

### 接入场景及相应方案和流程说明
**场景1：只需要id，不需要登录**

1. 调用Config接口，即可获取当前当前账号的id及其他相关信息[详见Config接口](./native/interfaces/Config.md)
2. ISV在自己的系统中，保存工作圈id和自己系统账号的对应关系即可。



**场景2：需要id并单点登录**

1. 调用Config获取当前账号信息[详见Config接口](./native/interfaces/Config.md)
2. 调用CSPAuthCode接口，获取单点登录code[详见CSPAuthCode接口](./native/interfaces/CSPAuthCode.md)
3. 调用CIA平台的验证接口，验证code是否有效[详见CIA平台接口](http://dev.chanjet.com/page/apiHtml?detail=1-1704406315/1-1959429278.html)