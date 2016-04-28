### ISV应用使用工作圈IM开放能力文档
负责人：胡继红，翟刘振

#### ISV应用使用工作圈IM推送消息的案例         



##### 具体的案例数据

案例ISV的推送系统名称为创新，分配给的消息推送的From为50000001021，分配的appId为1021，应用的名称是：创新。推送的消息为：某员工的创新成功得了一等奖。

##### 消息发送步骤  

+ 1.1 首先发送申请邮件，工作圈会给ISV分配所需要的From和AppID，如上面示例中的得到的from为50000001021，appId为1021
	 
+ 1.2 发送参数。 

|参数名称 |	参数说明|此例中该参数的值|
|:-------------|:-------------|:-------------|
|to	     | 消息接收人的UserID|60000001366|
|orgId	     | 消息接收人所在的企业标识|90000704377|
|alert	     | 消息的摘要|恭喜您，您的创新成果获得了国家一等奖|
|from	     | ISV在工作圈中分配到的消息发送标识|50000001021|
|appId	     | ISV在工作圈中轻应用标识|1021|   



其余的非必需参数，可以参见：[openpush.md](./im/openpush.md)   
	 
+ 1.3 后台直接编辑消息发送    
+ 1.3.1 打开网页: [网页地址](http://integzq.chanjet.com/openim/index.html) 
+ 1.3.2 编辑如下：![](http://gitlab.rd.chanjet.com/gongzuoquan/isv-dev-doc/raw/master/im/para.png)    
+ 1.3.3 点击 生成签名 按钮 ，生成签名：6f401b288f681230b45185581c8bfa76 ，把这个值填入sign的输入框中。
+ 1.3.4 点击 发送消息 按钮，发送消息，结果是：
![](http://gitlab.rd.chanjet.com/gongzuoquan/isv-dev-doc/raw/master/im/result.png)  

+ 1.4 通过java代码直接的调用rest服务推送消息：  

~~~
    public static HttpClientUtils	httpClientUtils	= HttpClientUtils.getInstance();
    public static String url = "http://integzq.chanjet.com/notify/web/openim/push";
	public static String pushMsg(String to, String alert, String orgId, String appId) 
			throws IOException
	{
		List<NameValuePair> params = new ArrayList<>();
		params.add(new NameValuePair("to", to));
		/**
		 * 其他的变量类似处理
		 * */
		String body = httpClientUtils.postResponse(url, params, Charsets.UTF8, false, null);
		return body;
	}
	
	/**
   * 执行一个POST请求
   * 
   * @param post
   *          post参数
   * @param throwExceptionIfAbNormal
   *          非200状态码时是否抛出异常
   * @return 执行的POST操作
   * @throws IOException
   *           任何网络IO异常或者非200状态码异常
   */
  public PostMethod post(PostMethod post, boolean throwExceptionIfAbNormal) throws IOException {
    execute(post, throwExceptionIfAbNormal, EMPTY_COOKIES);
    return post;
  }

/**
   * 执行一个GET/POST请求
   * 
   * @param method
   *          post参数
   * @param throwExceptionIfAbNormal
   *          非200状态码时是否抛出异常
   * @param cookies
   *          Cookie对象
   * @return {@link HttpState} 请求返回的Cookie结果，如果有的话
   * @throws IOException
   *           任何网络IO异常或者非200状态码异常
   */
  public HttpState execute(HttpMethod method, boolean throwExceptionIfAbNormal, Cookie... cookies)
      throws IOException {
    HttpState state = new HttpState();
    if (cookies != null && cookies.length > 0) {
      state.addCookies(cookies);
    }
    if (method.getParams().getParameter(HttpMethodParams.COOKIE_POLICY) == CookiePolicy.DEFAULT) {
      // 默认使用浏览器兼容模式，手动传递的Cookie协议不做任何限制
      // 解决cookie不规范的问题
      method.getParams().setCookiePolicy(CookiePolicy.BROWSER_COMPATIBILITY);
    }
    //noinspection UnusedAssignment
    int statusCode = -1;
    // count httpClient executeTime
    long startAt = System.currentTimeMillis();
    try {
      statusCode = httpClient.executeMethod(null, method, state);
    } catch (IOException ioe) {
      method.releaseConnection();
      throw ioe;
    }

    if (log.isDebugEnabled()) {
      log.info("httpclient url: {} ||| costTime: {}", method.getURI().toString(),
          String.valueOf(System.currentTimeMillis() - startAt));
    }

    if (throwExceptionIfAbNormal && statusCode != 200) {
      method.releaseConnection();
      throw new IOException("abnormal, status code:" + statusCode + ", uri:" + method.getURI());
    }
    return state;
  }
	
~~~

+1.5   一，通过浏览器调试模式，验证对方是否收到消息，如下图：
![](http://gitlab.rd.chanjet.com/gongzuoquan/isv-dev-doc/raw/master/im/valid.png)  

二，我们也可以安装集测环境手机端的工作圈运行的环境，这样能够在手机端直接的收到推送的消息。


2.  具体Rest服务说明，见 [openpush.md](./im/openpush.md)