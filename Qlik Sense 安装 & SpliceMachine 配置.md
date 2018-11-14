# 安装 Qlik Sense

- 在 Qlik Sense [官网][1]下载安装包
官网下载需要填写信息，这里有绕过填写表单的[官方下载地址][2]
- 直接双击安装

# 安装 SpliceMachine ODBC

- 同样的，SpliceMachine ODBC 也需要填写表单，这里提供[官方下载地址][3]
- 双击 **splice_odbc_setup_64bit_2.7.51.0.msi** 安装 SpliceMachine ODBC
- 开始菜单搜索 **64-bit ODBC Administrator** 并启动
- 正常情况下在 **系统 DSN** 选项卡里会出现 `Splice DSN` 一项
 ![64-bit ODBC Administrator 配置界面][4]
- 双击 **Splice DSN**，在 **User**、**Password**、**Server** 处分别填写 `splice`、`密码`、`服务器地址` 和端口号 `1527`
 ![SpliceMachine ODBC 配置界面][5]
- 点击 **Test**，验证连接，最后点击 **OK** 保存退出

# 配置 Qlik Sense 连接 SpliceMachine

- 运行 Qlik Sense，并创建登录账号
- 点击 **创建新应用程序**，填写 `splice`（自定义）
- 进入刚创好的 **splice** 中，点击 **从文件和其他源添加数据**
 ![创建新应用程序][6]
- 到 **连接到新的数据源** 选项卡，点击 **ODBC**
 ![连接到新的数据源][7]
- 点击 **系统 DSN** 下的 **Splice DSN 64**，填写用户名和密码
 ![创建新连接 ODBC][8]
- 点击创建，完成新建连接

# 配置 Qlik Sense 使用 SpliceMachine 数据

- 回到 **从文件和其他源添加数据** 界面，**点击脚本编辑器**
- 安照图片指示操作
 ![脚本编辑器界面][9]
- 进入应用程序视图 
 ![进入应用程序视图][10]
- 新建一个工作表并进入
- 点击**编辑**按钮
 ![编辑按钮][11]
- 按照指示就可以数据分析了
 ![完成][12]

**至此，Qlik Sense 与 SpliceMachine 的配置就完成了**

 [1]: https://www.qlik.com/us/
 [2]: https://da3hntz84uekx.cloudfront.net/sense/production/Qlik_Sense_Desktop_setup.exe
 [3]: https://s3.amazonaws.com/splice-releases/odbc-driver/win64/splice_odbc_setup_64bit_2.7.51.0.msi
 [4]: https://s1.ax2x.com/2018/11/14/5zbkih.png
 [5]: https://s1.ax2x.com/2018/11/14/5zb8mH.png
 [6]: https://s1.ax2x.com/2018/11/14/5zb2bA.png
 [7]: https://s1.ax2x.com/2018/11/14/5zbSZN.png
 [8]: https://s1.ax2x.com/2018/11/14/5zbxD9.png
 [9]: https://s1.ax2x.com/2018/11/14/5zpBDy.png
 [10]: https://s1.ax2x.com/2018/11/14/5zpFpX.png
 [11]: https://s1.ax2x.com/2018/11/14/5zpToJ.png
 [12]: https://s1.ax2x.com/2018/11/14/5zbnWe.png
