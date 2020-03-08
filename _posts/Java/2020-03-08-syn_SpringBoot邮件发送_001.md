---
layout: post
title:  "SpringBoot 发送富文本邮件"
date:   2020-03-08
tags:  syn
categories: Java
---

1. 第一步：引入JavaMailSender

	- 请注意：在引入JavaMailSender时，只能在带有@Component中引入。在其他静态类中引入会出现空指针报错。如果需要在静态类中引用，可以使用传值的方式将其传入需要使用的静态类中。
	
	```java
	@Autowired
	JavaMailSender mailSender;
	```
	
2. 第二步：配置application.properties中的邮件信息

  * 此处配置示例为163邮箱，如果使用QQ邮箱配置方式有所不同

  ```java
  #配置发送邮件相关信息
  spring.mail.host=smtp.163.com  //邮箱类型
  spring.mail.username=你的邮箱
  spring.mail.password=你的邮箱授权码
  #下面一般不用动
  spring.mail.default-encoding=UTF-8
  spring.mail.properties.mail.smtp.connectiontimeout=5000 
  spring.mail.properties.mail.smtp.timeout=3000
  spring.mail.properties.mail.smtp.writetimeout=5000
  spring.mail.properties.mail.smtp.auth=true
  spring.mail.properties.mail.smtp.starttls.enable=true
  spring.mail.properties.mail.smtp.starttls.required=true
  spring.mail.properties.mail.smtp.socketFactory.class=javax.net.ssl.SSLSocketFactory
  spring.mail.properties.mail.smtp.port=465
  spring.mail.properties.mail.smtp.socketFactory.port=465
  ```


3. 第三步：实现发送功能

	* 此处由于是在静态类中调用，故JavaMailSender是以参数的形式传过来的

	```java
//在类的上方加入@Component注解
	    //发送富文件消息，可带附件
    public void send(String content,String receiver,JavaMailSender javaMailSender){
	        //建立邮件消息
	        MimeMessage mimeMailMessage=javaMailSender.createMimeMessage();
	        MimeMessageHelper helper;
	        try {
	            helper = new MimeMessageHelper(mimeMailMessage,true);
	            //发送者（必须和配置文件中的相同）
	            helper.setFrom("发件人邮箱");
	            //接收者
	            helper.setTo(“收件人邮箱”);
	            //发送的标题
	            helper.setSubject("发送的标题");
	            //发送的内容
	            helper.setText(content,true);
	            //发送的附件（以File的格式发送）
	            helper.addAttachment(file.getName(), file);
	            //发送
	            javaMailSender.send(mimeMailMessage);
	        }catch (Exception e){
	            logger.info("邮件发送失败！失败原因："+e.getMessage());
	        }
	    }
	```
	
	

---

[原文链接](https://www.cnblogs.com/itmyhome/p/4131284.html)

