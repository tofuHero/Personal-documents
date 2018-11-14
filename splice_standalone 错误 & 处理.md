# SpliceMachine Standalone 错误 & 解决方案

## splice shell 默认数据库账号 & 密码

账号：splice

密码：admin

## 错误 08006

### 描述

执行 `splice> analyze table t;` 和 `splice> analyze schema myschema;` 语句后出现如下信息

```splice shell
错误 08006：遇到了网络协议错误，连接已终止：请求的命令遇到未构建的且特定于实现的情况，其中不存在已构建的消息（服务器上的 derby.log 文件中可能提供了其他信息）

错误 08006：DERBY SQL error: SQLCODE: -1, SQLSTATE: 08006, SQLERRMC: 检测到通信错误：{0}。::SQLSTATE: XJ001Java 异常：“java.lang.NullPointerException：java.io.IOException”。::SQLSTATE: XJ001Java 异常：“：java.lang.NullPointerException”。
```

后中断与服务端链接

### 解决方案：

暂无，可能是节点（虚拟机）网络质量不够好，也可能是分配的虚拟硬件资源过低

---

## 错误 42X01

### 描述

执行 `BINARY_EXPORT` 命令，如 `splice> binary_export('/test/', true, 'parquet') select id from player where id > 1;` 报错，内容如下

```splace shell
错误 42X01：语法错误：Encountered "binary_export" at line 1, column 1。
发出 "help" 命令，以了解有关 IJ 命令语法的一般信息。
任何无法识别的命令都将被视为可能的 SQL 命令并直接执行。
请查阅您的 DBMS 服务器参考文档，以了解您的服务器所支持 SQL 语法的详细信息。
```

### 解决方案

暂无，可能是 BUG，可以用 export() 代替

---

## 错误 42X04

### 描述

执行 `splice> insert into player values(2,'Tom', man);` 后出现如下信息

```splice shell
错误 42X04：列“MAN”不在 FROM 列表的任何表中，或者它出现在 join 规范内但超出 join 规范的作用域，或者它出现在 HAVING 子句中但不在 GROUP BY 列表中。如果这是 CREATE 或 ALTER TABLE 语句，则“WMAN”不是目标表中的列。
```

### 解决方案

检查表的数据类型，一般是因为数据类型不匹配造成的，更正即可 `splice> insert into player values(2,'Tom', 'man');`

---