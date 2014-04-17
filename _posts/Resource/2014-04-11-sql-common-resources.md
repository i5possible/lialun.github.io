---
layout: post
title: SQL常用语句
category: resource
tags: SQL
keywords: sql
description: 
---

## SQL常用语句
上年纪了，总是记不住啊~

### 查找表的主键和索引
{% highlight mysql %}
select k.CONSTRAINT_NAME, k.COLUMN_NAME, t.CONSTRAINT_TYPE, t.CONSTRAINT_NAME, k.ORDINAL_POSITION from information_schema.table_constraints t join information_schema.key_column_usage k using (constraint_name,table_schema,table_name) where t.table_schema = 'violation' and t.table_name = 'carinfo'
{% endhighlight %}

### 显示某一列出现过N次的值
{% highlight mysql %}
SELECT id FROM tbl GROUP BY id HAVING count(*) = N;
{% endhighlight %}

### 计算两个日子间的工作日
所谓工作日就是除出周六周日和节假日。
{% highlight mysql %}
SELECT COUNT(*) FROM calendar WHERE d BETWEEN Start AND Stop AND DAYOFWEEK(d) NOT IN(1,7) AND holiday=0;
{% endhighlight %}

### 时间差
单位为秒。    
除以60就是所差的分钟数，除以3600就是所差的小时数，再除以24就是所差的天数。
{% highlight mysql %}
UNIX_TIMESTAMP(dt2) - UNIX_TIMESTAMP(dt1)
{% endhighlight %}

### 查看数据库数据大小
{% highlight mysql %}
SELECT table_schema AS 'Db Name', Round( Sum( data_length + index_length ) / 1024 / 1024, 3 ) AS 'Db Size (MB)', Round( Sum( data_free ) / 1024 / 1024, 3 ) AS 'Free Space (MB)' FROM  information_schema.tables GROUP BY table_schema;
{% endhighlight %}
