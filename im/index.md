### ISV应用使用工作圈IM开放能力文档
负责人：胡继红，翟刘振

1.  接入ISV描述和要求
	ISV的接入，是作为工作圈中一个轻应用的形式接入，如下图：
![Alt text]()(./5ec700a5-0b37-4bad-b3d4-4934103dba42.png)


所以每一个ISV都会有一个唯一的appId来标识这个ISV，一个对应的appName来简要的说明这个ISV的功能。例如：任务这个轻应用的appId 为8，appName为任务。

> appId 为一个轻应用的唯一标识，是畅捷通的分配给ISV凭证。

ISV在使用工作圈的IM开放能力之前，需要人工通过邮件的方式，申请ISV接入需要的的数据，对应的数据变量会在邮件中有详细的说明。

2. 接入的过程

	我们按照一个具体的案例来说明，案例ISV的推送系统名称为创新，分配给的消息推送的From为1001，分配的appId为101，推送的消息为：某员工的创新成功得了一等奖。

	具体发送的测试页面是：
	http://integzq.chanjet.com/openim/index.html

   参数页面说明：
   
![Alt text]()(./d8a77ab8-f9bb-4b1a-9a81-ad8297b2031f.png)

   3. 具体方法说明，见[openpush.md]()(./openpush.md)

