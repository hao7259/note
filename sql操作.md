## sql操作

### DDL：数据定义语言

```sql
create database db1; -- 创建数据库
drop database db1; -- 删除数据库
use database db1; -- 使用数据库
show database(); -- 显示正在使用的数据库 
```

### DML：数据操作语言

```sql
show tables; -- 显示所有表
CREATE TABLE tablename(
  id int,
  username varchar(20),  
  age int
);
desc tablename -- 显示表名称
alter table tablename add score int -- 添加列
drop tablename -- 删除表
alter table tablename rename to student; -- 重命名表
alter table old_tablename change new_tablename int -- 修改列名和类型
alter table tablename drop score; -- 删除一列
delete from stu where username='张三' -- 删除一行
insert into stu(id,name)values(1,'XX'); -- 添加数据
insert into stu values(1,'XX',18,560); -- 添加数据
```

### DQL：数据库查询语言

```sql
select username AS '名字',phone AS '电话号' FROM stu where id=3;
select * FROM stu where id>3;
```





## JDBC

————java连接数据库

1.注册驱动

```java
DriverManger.register(new Driver());
```

2.加载驱动

```java
Class.forName("com.mysql.cj.jdbc.Driver");
```

3.获取与数据库的连接

```java
Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/db2","root", "root");
```

4.获取执行sql的对象

```java
Statement stmt = conn.createStatement();
```

5.编写sql语句

```java
String sql = "insert into student values(null,'xx',18,'男','520');";
```

6.执行sql语句

```java
stmt.execute(sql);
```

7.关闭资源

```java
stmt.close();
conn.close();
```

