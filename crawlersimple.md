### crawlersimple

###### 豆瓣网站

简单的用httpclient做爬虫

* mavenrepository搜索slf4j进行日志技术依赖

* 将下面内容复制粘贴

  <!-- https://mvnrepository.com/artifact/org.slf4j/slf4j-log4j12 -->
  <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>slf4j-log4j12</artifactId>
      <version>1.7.25</version>
      <scope>test</scope>
  </dependency>

* 创建class

```
//建立一个新的请求客户端
CloseableHttpClient httpClient = HttpClients.createDefault();

//使用HttpGet方式请求网址
HttpGet httpGet = new HttpGet("https://movie.douban.com");
//设置请求头信息，鉴权
httpGet.setHeader("User-Agent","Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.105 Safari/537.36");
// 设置配置请求参数
RequestConfig requestConfig = RequestConfig.custom().setConnectTimeout(35000)// 连接主机服务超时时间
        .setConnectionRequestTimeout(35000)// 请求超时时间
        .setSocketTimeout(60000)// 数据读取超时时间
        .build();
// 为httpGet实例设置配置
httpGet.setConfig(requestConfig);
// 执行get请求得到返回对象
//获取网址的返回结果
CloseableHttpResponse response =httpClient.execute(httpGet);

//获取返回结果中的实体
if (response.getStatusLine().getStatusCode() == 200){
    HttpEntity entity = response.getEntity();
    String content=EntityUtils.toString(entity,"utf8");



//将返回的实体输出

    System.out.println(content);
```

### Java爬虫入门到精通目录

[一、爬虫入门程序](https://blog.csdn.net/weixin_43235209/article/details/104570968)

[二、Get请求](https://blog.csdn.net/weixin_43235209/article/details/104571926)

[三、Post请求](https://blog.csdn.net/weixin_43235209/article/details/104572134)

[四、连接池](https://blog.csdn.net/weixin_43235209/article/details/104572408)

[五、设置请求的配置信息](https://blog.csdn.net/weixin_43235209/article/details/104579414)

[六、HTML解析器 jsoup](https://blog.csdn.net/weixin_43235209/article/details/104579988)

[七、Java爬虫案例（一）](https://blog.csdn.net/weixin_43235209/article/details/104998850)

[八、WebMagic介绍](https://blog.csdn.net/weixin_43235209/article/details/105104416)

[九、WebMagic入门程序](https://blog.csdn.net/weixin_43235209/article/details/105104979)

[十、WebMagic之PagePageProcessor解析数据](https://blog.csdn.net/weixin_43235209/article/details/105121923)

[十一、WebMagic之Pipeline存储数据](https://blog.csdn.net/weixin_43235209/article/details/105128287)

[十二、WebMagic爬虫的相关配置](https://blog.csdn.net/weixin_43235209/article/details/105128649)

