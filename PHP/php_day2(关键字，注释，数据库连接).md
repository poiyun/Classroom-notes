关键字
---
系统关键字不区分大小写，拿`function`举例
```
functoin name(){

}
Function name(){

}
```
调用时记得加分号
```
name();
```
注释
---
PHP的闭合标签`<?PHP ?>`末尾的`?>`可以省略
PHP的注释分为单行注释和多行注释
```
#这是单行

/*
这
是
多
行
*/
```
连接数据库
--------
目前常用的PHP版本分为PHP5.x和PHP7.x，两个版本相差巨大，PHP5的连接数据库方法在PHP7.x中早已废弃

####数据库连接(PHP5.x)
```
<?php
#防止网页乱码
header('context-type:text/html;charset=utf-8');
#内置函数连接数据库，里面有两个参数，数据库地址+用户名
$link=mysql_connect('localhost:3306','root');
#设置数据库编码
mysql_set_charset('utf8');
#选择数据库，这里是选择了一个名为MYsql的数据库
mysql_select_db('mysql');
#写sql语句，这里是列出所有的表
$sql='show tables';
#执行SQL语句
$rel=mysql_query($sql);
#获取数据
while($row=mysql_fetch_assoc($rel))
{
    echo '表的名字是',$row['Tables_in_mysql'],<br/>
}
?>
```
####数据库连接(PHP7.x)
```
<?php
$servername="localhost";
$username="这里替换成你的用户名";
$password="这里写你的密码";

#创建连接
$conn=new mysqli($servername,$username,$password);

#检查连接
if($conn->connect_error){
    die("连接失败".$conn->connect_error);
}
echo "连接成功";
$sql='show tables from mysql';
$result=$conn->query($sql);
if($result->nim_rows>0){
    while($row=$result->fetch_assoc()){
        echo '表的名字是',$row['Tables_in_mysql'],<br/>
    }
}else{
    echo "0 结果"
}
$conn->close();

?>
```