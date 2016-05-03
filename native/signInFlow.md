### 接入方案及流程说明
**场景1：只需要id，不需要登录**

调用Config接口，即可获取当前当前账号的id及其他相关信息;ISV在自己的系统中，保存工作圈id和自己系统账号的对应关系即可。

[详见Config接口](./native/interfaces/Config.md)


**场景2：需要id并单点登录**
1. 调用Config获取当前账号信息[详见Config接口](./native/interfaces/Config.md)
2. 调用CSPAuthCode接口，获取单点登录code[详见CSPAuthCode接口](./native/interfaces/CSPAuthCode.md)
3. 调用CIA平台的验证接口，验证code是否有效[详见CIA平台接口](./)