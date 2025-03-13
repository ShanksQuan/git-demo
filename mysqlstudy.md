# MySQL
#### 关系型数据库（RDBMS）
关系型数据库管理系统（Relational Database Management System，RDBMS）是建立在关系模型数据库理论基础上的数据库系统。关系模型数据库是指数据以表格的形式存储在数据库中，每一行和每一列都与其他行和列相关联。关系模型数据库的优点是数据结构简单，易于理解和操作，便于存储和检索数据。

## MySQL数据库
### 数据模型
MySQL数据库是关系型数据库管理系统（RDBMS）的一种，它使用SQL语言作为查询语言。MySQL数据库的结构化查询语言（Structured Query Language，SQL）是一种声明性语言，它使用关系代数来处理数据。
数据库和表
MySQL数据库由数据库和表组成。数据库是一组相关表的集合，数据库中的表共享相同的结构。数据库可以包含多个表，每个表可以包含多个行和列。

### SQL语言
SQL的通用语法
可以单行或者多行执行SQL语句。SQL语句以分号（;）结尾。
不区分大小写
注释使用--或#。

### 常用SQL命令
包括SELECT、INSERT、UPDATE、DELETE、CREATE、ALTER、DROP、TRUNCATE、GRANT、REVOKE、COMMIT、ROLLBACK等命令。
### SQL语句分类
DDL（Data Definition Language，数据定义语言）：用于定义数据库对象，如数据库、表、视图、索引等。
DML（Data Manipulation Language，数据操纵语言）：用于操作数据库对象，如插入、删除、更新数据。
DCL（Data Control Language，数据控制语言）：用于控制数据库的访问权限，如事务处理、连接管理等。
DQL（Data Query Language，数据查询语言）：用于查询数据库对象，如检索、搜索数据。

### DDL
###### DDL表操作命令
```sql
CREATE DATABASE：创建数据库。
CREATE TABLE：创建表。
create table table_name (
     column_name data_type constraint,
     id int comment '主键',
     name varchar(50) not null comment '姓名',
     age int comment '年龄'
    ...)：创建表。
```
```sql
show tables：//显示当前数据库中的所有表。
DESC table_name：//显示表的结构。
ALTER TABLE：//修改表。
DROP TABLE：//删除表。
```
###### DDL表操作数据类型
```sql
int：整型
varchar(n)：字符串，最大长度为n
text：长文本
date;datetime：日期时间
```
###### DDL表操作修改
```sql
//添加字段
alter table table_name add column_name data_type (comment '注释');
//删除字段
alter table table_name drop column_name;
//修改字段数据类型
alter table table_name modify column_name data_type ；
//修改字段名称
alter table table_name change column_name new_column_name data_type;
//修改表名
alter table table_name rename to new_table_name;
```
###### DDL表操作删除

```sql
drop table table_name：//删除表。
truncate table table_name：//清空表，删除所有数据。
```
###### DDL小结
DDL命令用于定义数据库对象，包括创建数据库、创建表、修改表、删除表等。
### DML
完成数据的增删改查操作。

###### DML插入数据
```sql
insert into table_name (column1, column2,...) values (value1, value2,...);//给指定字段赋值
insert into table_name values (value1, value2,...);//给全部字段赋值，需要保证字段顺序一致。
insert into table_name (column1, column2,...) values (value1, value2,...),(value1, value2,...);//插入多条记录。
//注意插入数据时，字段类型要与表结构一致。
//字符串与日期型数据需要加单引号。
//插入数据的大小应该小于表的最大值。
```

###### DML修改数据
```sql
update table_name set column1=value1, column2=value2,... where condition;//条件可以没有
```
###### DML删除数据
```sql
DELETE FROM table_name WHERE condition;//条件也可以没有
//不能删除表，只能删除数据。
//不能删除某一个字段，只能整表删除。
```
###### DML小结
DML命令用于操作数据库对象，包括插入数据、更新数据、删除数据等。

### DQL
完成数据的查询操作。
##### DQL基础语法
```sql
SELECT
    //字段列表
FROM 
    //表名列表
WHERE 
    //条件列表
GROUP BY 
    //分组字段列表
HAVING 
    //分组后过滤条件
ORDER BY 
    //排序字段列表
LIMIT 
    //分页参数
```
###### DQL基础查询
```sql
SELECT column1, column2,... FROM table_name WHERE condition;//查询指定字段
SELECT * FROM table_name WHERE condition;//查询全部字段
SELECT DISTINCT column1, column2,... FROM table_name WHERE condition;//查询指定字段的不同值
```
设置别名
```sql
SELECT column1 AS c1, column2 AS c2,... FROM table_name WHERE condition;//给字段设置别名
```
去除重复记录
```sql
SELECT DISTINCT column1, column2,... FROM table_name WHERE condition;
```
###### DQL条件查询
```sql
select * from table_name where condition1 and condition2 and condition3;
/*
比较运算符:
=   等于
>   大于
<   小于
>=  大于等于
<=  小于等于
<>  不等于
!=  不等于
BETWEEN and介于
LIKE  使用_和%作为通配符的模糊查询
IN  范围查询
IS NULL 为空
逻辑运算符:
AND && 与
OR  || 或
NOT !  非
*/
```
###### 聚合函数
将一列数据作为整体进行纵向的统计，如求和、平均值、最大值、最小值等。
```sql
SELECT COUNT(*) FROM table_name;//计算行数
SELECT SUM(column1) FROM table_name;//求和
SELECT AVG(column1) FROM table_name;//平均值
SELECT MAX(column1) FROM table_name;//最大值
SELECT MIN(column1) FROM table_name;//最小值
```
###### DQL分组查询
将数据按照指定字段进行分组，然后对分组后的结果进行聚合操作。
```sql
SELECT column1, column2,... FROM table_name where condition
GROUP BY column1, column2,... 
Having condition;
//where_condition为可选条件，用于过滤分组。
//Having条件为分组后过滤条件，与where条件类似。
```