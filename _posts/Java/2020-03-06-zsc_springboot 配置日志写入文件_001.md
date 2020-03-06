---
layout: post
title:  "springboot 配置日志写入文件"
date:   2020-03-06
tags:  zsc
categories: Java
---

* 配置application.properties文件

    ```properties
    #日志配置
    logging.level.root=info
    logging.level.org.springframework.web=DEBUG
    logging.file.name=log/server.log
    logging.file.max-history=365
    logging.file.max-size=10MB
    ```

* 其他常用配置说明

| Spring Environment                | 系统属性                 | 说明                     |
| --------------------------------- | ------------------------ | ------------------------ |
| logging.exception-conversion-word | LOG_EXCEPTION_CONVERSION |                          |
| logging-file                      | LOG_FILE                 | 日志文件名               |
| logging.file.max-size             | LOG_FILE_MAX_SIZE        | 日志文件的最大容量       |
| logging.file.max-history          | LOG_FILE_MAX_HISTORY     | 日志文件的最长保存时间   |
| logging.path                      | LOG_PATH                 | 日志文件保存路径         |
| logging.pattern.console           | CONSOLE_LOG_PATTERN      | 使用控制台输出的日志模式 |
| logging.pattern.dateformat        | LOG_DATEFORMAT_PATTERN   | 日志时间格式             |
| logging.pattern.file              | FILE_LOG_PATTERN         | 日志文件中日志的模式     |
| logging.pattern.level             | LOG_LEVEL_PATTERN        | 在渲染日志级别时的格式   |
| PID                               | PID                      | 当前的进程ID             |
|                                   |                          |                          |

