# Zeppelin 介绍

---

# 安装

**注：** Zeppelin 版本为 0.8.0

## 匿名访问方式
- 下载 [**Zeppelin**][1] 工具
- 上传压缩包至服务器任意路径（例如：/root/app/softwares/）
- 并解压到服务器任意路径（例如：/root/app/models/）
`tar -zxvf /root/app/softwares/zeppelin-0.8.0-bin-all.tgz -C /root/app/models`
- 执行 `/root/apps/models/zeppelin-0.8.0-bin-all/bin/zeppelin-daemon.sh start` 启动 **zeppelin**
- 通过浏览器访问 `http://hostip:8080` 即可进入 **zeppelin** 界面，默认匿名模式

## 启用用户验证

- 重命名文件 **zeppelin-site.xml.template** 为 **zeppelin-site.xml**、**shiro.ini.template** 为 **shiro.ini**
 - `mv /root/apps/models/zeppelin-0.8.0-bin-all/conf/zeppelin-site.xml.template /root/apps/models/zeppelin-0.8.0-bin-all/conf/zeppelin-site.xml`
 - `mv /root/apps/models/zeppelin-0.8.0-bin-all/conf/shiro.ini.template /root/apps/models/zeppelin-0.8.0-bin-all/conf/shiro.ini`
- 编辑 **zeppelin-site.xml** 文件 `vim /root/apps/models/zeppelin-0.8.0-bin-all/conf/zeppelin-site.xml`，定位到 **407** 行，将 **true** 改为 **false** 禁止匿名登录，如下所示
 ```xml
<property>
  <name>zeppelin.anonymous.allowed</name>
  <value>false</value>
  <description>Anonymous user allowed by default</description>
</property>
 ```
- 编辑 **shiro.ini** 文件 `vim /root/apps/models/zeppelin-0.8.0-bin-all/conf/shiro.ini`，定位到 **18** 行，内容如下所示
 ```ini
[users]
# List of users with their password allowed to access Zeppelin.
# To use a different strategy (LDAP / Database / ...) check the shiro doc at http://shiro.apache.org/configuration.html#Configuration-INISections 
# To enable admin user, uncomment the following line and set an appropriate password.
#admin = password1, admin
 user1 = password2, role1, role2
 user2 = password3, role3
 user3 = password4, role2
 ```
如果想启用 admin 账户则把 `admin = password1, admin` 前的 `#` 去掉即可。用户名，密码按照文本中的样式修改即可

至此 **Zeppelin** 安装完成

 [1]: https://zeppelin.apache.org/
