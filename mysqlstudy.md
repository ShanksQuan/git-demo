# MySQL
#### 关系型数据库（RDBMS）
关系型数据库管理系统（Relational Database Management System，RDBMS）是建立在关系模型数据库理论基础上的数据库系统。关系模型数据库是指数据以表格的形式存储在数据库中，每一行和每一列都与其他行和列相关联。关系模型数据库的优点是数据结构简单，易于理解和操作，便于存储和检索数据。

#### MySQL数据库
##### 数据模型
MySQL数据库是关系型数据库管理系统（RDBMS）的一种，它使用SQL语言作为查询语言。MySQL数据库的结构化查询语言（Structured Query Language，SQL）是一种声明性语言，它使用关系代数来处理数据。
数据库和表
MySQL数据库由数据库和表组成。数据库是一组相关表的集合，数据库中的表共享相同的结构。数据库可以包含多个表，每个表可以包含多个行和列。

##### SQL语言
SQL的通用语法
可以单行或者多行执行SQL语句。SQL语句以分号（;）结尾。
不区分大小写
注释使用--或#。

##### 常用SQL命令
包括SELECT、INSERT、UPDATE、DELETE、CREATE、ALTER、DROP、TRUNCATE、GRANT、REVOKE、COMMIT、ROLLBACK等命令。
##### SQL语句分类
DDL（Data Definition Language，数据定义语言）：用于定义数据库对象，如数据库、表、视图、索引等。
DML（Data Manipulation Language，数据操纵语言）：用于操作数据库对象，如插入、删除、更新数据。
DCL（Data Control Language，数据控制语言）：用于控制数据库的访问权限，如事务处理、连接管理等。
DQL（Data Query Language，数据查询语言）：用于查询数据库对象，如检索、搜索数据。

##### DDL
###### DDL表操作命令
CREATE DATABASE：创建数据库。
CREATE TABLE：创建表。
create table table_name (
    column_name data_type constraint,
    id int comment '主键',
    name varchar(50) not null comment '姓名',
    age int comment '年龄'
    ...)：创建表。
show tables：显示当前数据库中的所有表。
DESC table_name：显示表的结构。
ALTER TABLE：修改表。
DROP TABLE：删除表。
###### DDL表操作数据类型
int：整型
varchar(n)：字符串，最大长度为n
text：长文本
date;datetime：日期时间


##### DML
INSERT INTO：插入数据。
UPDATE：更新数据。
DELETE：删除数据。

##### DCL
COMMIT：提交事务。
ROLLBACK：回滚事务。

##### DQL
SELECT ：查询数据。  
SHOW DATABASES：显示所有数据库。  
SHOW TABLES：显示当前数据库中的所有表。  
DESCRIBE table_name：显示表的结构。  
