### 云服务器配置jdk和tomcat

------

#### 配置阿里云

* 购买服务器（ESC）
* 重置密码
* 使用termius连接服务器

#### jdk

* 下载jdk-8u261-linux-x64.tar.gz
* 云服务器的opt文件夹下新建文件夹jdk
* 将压缩包放入文件夹中
* cd  /opt/jdk  (进入文件夹)
* 使用命令解压 tar -zxvf jdk-8u261-linux-x64.tar.gz（完成出现一个文件夹）
* 配置环境变量 vi ~/.bashrc
* 按i进入编辑
* 添加

export JAVA_HOME=/opt/jdk/jdk1.8.0_261
export CLASSPATH=.:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
export PATH=$JAVA_HOME/bin:$PATH

* esc（退出） ：wq(保存)

* source ~/.bashrc 让环境变量生效

* 【vim /etc/profile 环境变量】

* 输入命令查看环境变量：

  echo $CLASSPATH

  echo $PATH

* java -version  检查

------

#### tomcat

* 下载apache-tomcat-9.0.38.tar.gz
* 放入文件夹opt 并新建文件夹 apache-tomcat-9.0.38
* 解压 tar -zxvf apache-tomcat-9.0.38.tar.gz

* 将压缩包放入文件夹中
* cd  /opt/apache-tomcat-9.0.38  (进入文件夹)
* 环境变量可配可不配
* 步骤

1.cd /opt/apache-tomcat-9.0.38

2.cd apache-tomcat-9.0.38

3.cd bin

4../catalina.sh

* \#启动tomcat, 在tomcat目录下 bin/startup.sh 
* #关闭tomcat, 在tomcat目录下 bin/shutdown.sh 

* 进入阿里云进行安全组添加

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191112140009583.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzE0OTk2NDIx,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191112140152509.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzE0OTk2NDIx,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191112140254828.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzE0OTk2NDIx,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/2019111214040495.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzE0OTk2NDIx,size_16,color_FFFFFF,t_70)

------

#### 防火墙

* ```java
  #停止firewall
  systemctl stop firewalld.service 
   
  #开启firewall
  systemctl start firewalld.service
   
  #禁止firewall开机启动
  systemctl disable firewalld.service 
   
  #查看默认防火墙状态（关闭后显示not running，开启后显示running）
  firewall-cmd --state
  1234567891011
  ```

  但是开启的时候，可能报这个错

  ```
  Failed to start firewalld.service: Unit firewalld.service is masked.
  1
  ```

  输入了下面这行命令：

  ```
  systemctl unmask firewalld.service
  ```

------

## 添加linux开放端口

只需要使用下面的命令，我们就可以访问 **8080** 端口

```
/sbin/iptables -I INPUT -p tcp --dport 8080 -j ACCEPT
```

------

参照网址：https://blog.csdn.net/qq_14996421/article/details/103027279