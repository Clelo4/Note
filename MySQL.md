# 1. 简介

## 1.1 名词解释

| 名词 | 解释 |
| --- | ---  |
| 数据库 | 数据库(database) 保存有组织的数据的容器(通常是一个文 件或一组文件) |
| DBMS | 数据库软件应称为DBMS(数据库管理系统) |
| 表(table) | 某种特定类型数据的结构化清单 |
| 模式(schema) | 关于数据库和表的布局及特性的信息 |
| 主键 | 一列(或一组列)，其值能够唯一区分表中每个行 | 
| SQL | 结构化查询语言(Structured Query Language)的缩写。SQL是一种专门用来与数据库通信的语言 |

## 1.2 主键

* 应该总是定义主键

### 1.2.1 主键限制规则

* 任意两行都不具有相同的主键值
* 每个行都必须具有一个主键值(主键列不允许NULL值)。
* 主键列允许由**多个字段**组合成

* 不要更新主键列中的值
* 不在主键列中使用可能会更改的值

# 2. MySQL

## 2.1 常用指令

| 指令 | 意思 |
| ---- | --------|
| SHOW DATABASES | 列出数据库 |
| SHOW TABLES | 列出当前数据库的所有表 |
| SHOW COLUMNS FROM test.user | 列出表test.user的所有字段 |
| SHOW STATUS | 用于显示广泛的服务器状态信息 |
| SHOW CREATE DATABASE test | 用来显示创建特定数据库test的MySQL语句 |
| SHOW CREATE TABLE user | 用来显示创建特定表user的MySQL语句 |
| SHOW GRANTS | 用来显示授予用户(所有用户或特定用户)的安全权限 |
| SHOW ERRORS和SHOW WARNINGS | 用来显示服务器错误或警告消息 |


## 2.2 注意事项

* SQL语句不区分大小写
  
  许多SQL开发人员喜欢对所有SQL关键字使用大写，而对所有列和表名使用小写
* ds f ds


## 2.3 常用MySQL操作

### 2.3.1 SELECT语句

```sql
SELECT a, b FROM user;
SELECT * FROM user;
```

> 注意：别使用*通配符，这会检索不需要的列，会降低检索和应用程序的性能

* 排序ORDER BY（默认ASC）

```sql
SELECT * FROM `user` ORDER BY id DESC, created_at; # created_at默认ASC排序
SELECT * FROM `user` ORDER BY id DESC, created_at ASC; # 选对id进行desc排序，如果相同再按照asc对created_at进行排序
```

* 限制数量

```sql
SELECT * FROM `user` LIMIT 10; # 获取前10个
```

* 分页

```sql
SELECT * FROM `user` ORDER BY id DESC, created_at ASC LIMIT 0, 5; # 从0开始的前5个
SELECT * FROM `user` ORDER BY id DESC, created_at ASC LIMIT 5, 3; # 从5开始的前3个，即5，6，7（0为开头）
SELECT * FROM `user` ORDER BY id DESC , created_at ASC LIMIT 3 OFFSET 5; # 从5开始的前3个（0为开头）
```

* DISTINCT关键字

```sql
SELECT DISTINCT email, verification_status  FROM `user` LIMIT 5 OFFSET 0;
```
输出：
example@gmail.com	1
123	0

```sql
SELECT email, verification_status  FROM `user` LIMIT 5 OFFSET 0;
```
输出
example@gmail.com	1
123	0
123	0
123	0
123	0

> 注意：不能部分使用DISTINCT DISTINCT关键字应用于所有列而 不仅是前置它的列


### 2.3.2 使用WHERE子句

```sql
SELECT email, verification_status  FROM `user` WHERE id BETWEEN 0 AND 10;
```

> 注意：在同时使用ORDERBY和WHERE子句时，应该让ORDER BY位于WHERE之后，否则将会产生错误

* WHERE子句操作符

| 操作符 | 说明 |
| ---- | ---- |
| = | 等于 |
| <> | 不等于 |
| != | 不等于 |
| < | 小于 |
| <= | 小于等于 |
| > | 大于 |
| >= | 大于等于 |
| BETWEEN | 在指定的两个值之间 |


* 空值检查

在创建表时，表设计人员可以指定其中的列是否可以不包含值。在
一个列不包含值时，称其为包含空值NULL。

> NULL 无值(no value)，它与字段包含**0**、**空字符串**或**仅仅包含空格**不同。


```sql
SELECT email, verification_status, id, verification_key  FROM `user` WHERE id <> 0 AND verification_key IS NULL;

SELECT email, verification_status, id, verification_key  FROM `user` WHERE id <> 0 AND verification_key NOT NULL;
```

* NULL与不匹配是不同的！！！

  * 在通过过滤选择出不具有特定值的行时，你 可能希望返回具有NULL值的行。但是，不行。因为未知具有 特殊的含义，数据库不知道它们是否匹配，所以在匹配过滤 或不匹配过滤时不返回它们。
  * 因此，在过滤数据时，一定要验证返回数据中确实给出了被 过滤列具有NULL的行。


  > 检索verification_key不等于A的所有日录，同时包括NULL
  ```sql
  SELECT * FROM `user` WHERE verification_key != 'A' OR verification_key is NULL; # 包括verification_key为NULL的数据
  SELECT * FROM `user` WHERE verification_key != 'A'; # 不包括verification_key为NULL的数据
  ```

### 2.3.3 组合WHERE子句

* AND和OR同时使用

加括号

* IN操作符

```sql
SELECT email, verification_status, id, verification_key  FROM `user` WHERE id IN (0, 1, 2, 3, 4, 5);
```

* NOT操作符

> ⚠️MySQL中的NOT： MySQL支持使用NOT对**IN**、**BETWEEN**和**EXISTS**子句取反，其他基本不支持


### 2.3.4 通配符

* LIKE操作符

在搜索子句中使用通配符，必须使用LIKE操作符

* %通配符

%表示任何字符出现任意次数（0个、1个或多个字符）

```sql
SELECT * FROM `user` WHERE email LIKE '1%3';
```

> 区分大小写：根据MySQL的配置方式，搜索可以是区分大小写的。如果区分大小写，'jet%'与JetPack 1000将不匹配

> %不匹配NULL：虽然似乎%通配符可以匹配任何东西，但有一个例外，即NULL。即使是WHERE prod_name LIKE '%'也不能匹配 值NULL的数据


* 下划线(_)通配符

下划线的用途与%一样，但下划
线只匹配单个字符而不是多个字符

### 2.3.5 使用MySQL正则表达式

```sql
SELECT * FROM `user` WHERE email REGEXP '.+3';
```


## 2.4 更新表

* 修改表名

RENAME TABLE old_table TO new_table;
ALTER TABLE old_table RENAME new_table;

* 修改列名

ALTER TABLE table_name RENAME COLUMN old_column_name TO new_column_name;


## NULL vs Empty ""

* NULL means absence of value (i.e. there is no value), while empty string means there is a string value of zero length.
* 在UNIQUE约束中，允许存在多个NULL，不允许存在多个empty ""，因为NULL代表未知，empty ""有实际意义。
* 举例：Address为NULL表示地址未填，empty ""表示该地址为空。

## LAST_INSERT_ID函数

LAST_INSERT_ID针对的是单个链接的，而不是整个MySQL，所以不会影响其他链接，也不会受其他链接影响，自然不需要锁或者事务管理。
