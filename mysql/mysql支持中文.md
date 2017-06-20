### 1，创建table的时候就使用utf8编码
```sql
create table entries2 (
        id     int auto_increment,
        title  text,
        content  text,
        posted_on  datetime,
        primary key (id)   
) character set = utf8;
```

### 2，修改已经有的table的编码
<p>当使用默认编码创建了一个table的时候，是不能支持中文的，这时候使用如下语句对table_name进行修改：</p>

```sql
alter table table_name convert to character set utf8;
```

### 备注
* 参考网址[http://www.cnblogs.com/livingintruth/p/3433259.html](http://www.cnblogs.com/livingintruth/p/3433259.html)
