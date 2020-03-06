---
layout: post
title:  "JDBC ResultSet转换为List及遍历数据"
date:   2020-03-06
tags:  syn
categories: Java
---

1. 如何将ResultSet的结果集转换为List
	```java
	sta = conn.createStatement();
	rs = sta.executeQuery("select * from e_user");
	ResultSetMetaData md = rs.getMetaData(); //获得结果集结构信息,元数据
	int columnCount = md.getColumnCount();   //获得列数 
	while (rs.next()) {
		Map<String,Object> rowData = new HashMap<String,Object>();
		for (int i = 1; i <= columnCount; i++) {
			rowData.put(md.getColumnName(i), rs.getObject(i));
		}
	}	
	list.add(rowData);
	```

2. 如何遍历ResultSet结果集中的行数据

	* 该功能由1的功能延伸实现，通过获得结果集结构信息和原数据的方式，在while循环中直接遍历当前行中的所有列。代码示例如下：

	```java
	ResultSetMetaData rmd=rs.getMetaData();//获得结果信息结构信息，元数据
	int columnCount = rmd.getColumnCount();//获得列数
	while (rs.next()){
		String content=contentText;
		//遍历当前行中的每一列数据,并进行富文本文件内容替换
		for (int z = 1; z <= columnCount; z++) {
		content=content.replaceAll("#"+rmd.getColumnName(z)+"#",rs.getString(z));
		}
		finalContent=finalContent+content;
	}
	```


3. 编程思路-将复杂功能简单换

* 在实现一个复杂功能时，可以通过模块化和封装的方式来实现简化逻辑复杂程度。这种思维的好处有：

	1. 单个类中的代码复杂程度和代码行数降低

	2. 有效理清思路，能快速设计大体实现办法

	3. 程序出错易于找到出错部分

