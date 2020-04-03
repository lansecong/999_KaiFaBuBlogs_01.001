---
layout: post
title:  "okHttp下载文件中文文件名乱码和springboot发送邮件附件中文名乱码"
date:   2020-04-03
tags:  zsc
categories: Java
---

### okHttp下载文件中文文件名乱码及请求头中文乱码

* URLDecoder类包含一个decode(String s,String charcter)静态方法,它可以将看上去乱码的特殊字符串转换成普通字符串
* URLEncoder类包含一个encode(String s,String charcter)静态方法,它可以将普通字符串转换成application/x-www-form-urlencoded MIME字符串
*   当URL地址中仅包含普通非中文字符串和application/x-www-form-urlencoded MIME字符串无须转换,而包含中文字符串的普通字符串则需要转换,换句话说,也就是说URL地址中有"中文字符串"传递时,才会考虑用到上面提到的两个类,这样就可以将传递过来的中文接受后,再还原成原来的中文字符串.如不转换,则通过URL传递过来的中文字符中会变成乱码,无法还原了

### springboot发送邮件附件中文名乱码

*  在添加中文名附件时通过调用MimeUtility的encodeWord方法。
 ```java

 helper.addAttachment(MimeUtility.encodeWord("signature_" + fileNameTempList.get(0).getFileName(), "utf-8", "B"), item);
 
```