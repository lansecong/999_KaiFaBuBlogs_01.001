---
layout: post
title:  "SpringBoot 发送富文本邮件"
date:   2020-03-08
tags:  syn
categories: Java
---

1. 第一步：引入JavaMailSender

	- 请注意：在引入JavaMailSender时，由于使用了spring的自动装配（@Autowired注解），只能在最上层的类中引入。如果在被调用的工具类中引入会出现空指针错误（原因：使用new关键字创建的对象不受Spring容器管理，无法注入）
	
	```java
	@Autowired
	JavaMailSender mailSender;
	```
	
2. 第二步：配置application.properties中的邮件信息

  * 此处配置示例为163邮箱，如果使用QQ邮箱配置方式有所不同

  ```properties
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
  # 这条语句什么意思？？？
  spring.mail.properties.mail.smtp.socketFactory.class=javax.net.ssl.SSLSocketFactory
  # 为什么是465端口？？？
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
	



------

附：Spring中Autowired注解出现空指针异常的原因总结

[原文链接](https://blog.csdn.net/yan3013216087/article/details/86680408?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task)