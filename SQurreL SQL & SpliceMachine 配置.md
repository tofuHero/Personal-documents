# SQurreL SQL

## 运行截图

![运行截图](https://s1.ax2x.com/2018/11/14/5zuLZr.png)

## 安装

- 下载 **SQuirreL SQL** [**下载地址**](http://www.squirrelsql.org/#installation)
- 确保电脑拥有 Java 运行环境
- 执行 `java -jar squirrel-sql-3.9.0-standard.jar` 按照提示安装，其中有可选的中文语言包

## 配置方式

### 驱动程序配置

- 启动 **SQuirreL SQL**，点击左侧 **驱动程序**
 ![驱动程序](https://s1.ax2x.com/2018/11/14/5zurid.png)
- 点击 **加号（+）** 并打开 **附加类路径** 选项卡
 ![添加驱动程序1](https://s1.ax2x.com/2018/11/14/5zucce.png)
- 点击 **增加**，选择连接 SpliceMachine 的 JDBC 后点击列出驱动程序,选择 **com.splicemachine.db.ClientDriver**
 ![添加驱动程序2](https://s1.ax2x.com/2018/11/14/5zu1by.png)
- 填写 **名字** 和 **地址示例** 字段，点击确定
 ![添加驱动程序3](https://s1.ax2x.com/2018/11/14/5zutnl.png)

### 创建到 SpliceMachine 的连接

- 点击 **别名**，新建 **别名（连接）**
- **名字：** 自定义、**地址：** SpliceMachine 数据库的地址、**用户名：** `splice`、**密码：** `admin`
 ![添加别名](https://s1.ax2x.com/2018/11/14/5zuIWJ.png)
- 双击刚刚添加的 **别名**，点击 **连接** 按钮即可使用  
 ![连接到数据库](https://s1.ax2x.com/2018/11/14/5zuAKX.png)
