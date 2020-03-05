---
layout: post
title:  "ShowMessage用法总结"
date:   2020-03-05 
tags:  zsc
categories: CloudBOS
---
 
### ShowMessage 用法总结
* 界面弹出提示信息，提醒用户。
* 方法 一
    * 参数说明
        * msg：提示信息
        * msgType：消息图标类型
    * 返回类型
        * 无返回值
```
void ShowMessage(string msg, MessageBoxType msgType = MessageBoxType.Notice);
```

* 方法 二
    * 参数说明
        * msg：提示信息
        * options：消息按钮类型
        * title：消息窗体标题
        * msgType：消息图标类型
    * 返回类型
        * 无返回值
```
void ShowMessage(string msg, MessageBoxOptions options, string title = "", MessageBoxType msgType = MessageBoxType.Notice);
```
* 方法 三
    * 参数说明
        * msg：提示信息
        * options：消息按钮类型
        * action：回调函数
        * title：消息窗体标题
        * msgType：消息图标类型
    * 返回类型
        * 无
```
void ShowMessage(string msg, MessageBoxOptions options,Action<MessageBoxResult> action, string title = "", MessageBoxType msgType = MessageBoxType.Notice);
```

* 方法 四
    * 参数说明
        * qLinkButtionMsgInfo：按钮链接信息
        * msg：提示信息
        * msgType：消息图标类型
    * 返回类型
        * 无
```
void ShowMessage(Queue<MsgInnerInfo> qLinkButtionMsgInfo, string msg, MessageBoxType msgType = MessageBoxType.Notice);
```

* 方法 五
    * 参数说明
        * qLinkButtionMsgInfo：按钮链接信息
        * msg：提示信息
        * options：界面按钮类型
        * title：消息提示界面标题
        * msgType：消息图标类型
    * 返回类型
        * 无
```
void ShowMessage(Queue<MsgInnerInfo> qLinkButtionMsgInfo, string msg, MessageBoxOptions options, string title = "", MessageBoxType msgType = MessageBoxType.Notice);
    ```

* 方法 六
    * 参数说明
        * qLinkButtionMsgInfo：按钮链接信息
        * msg：提示信息
        * options：界面按钮类型
        * action：回调函数
        * title：消息提示界面标题
        * msgType：消息图标类型
    * 返回类型
        * 无
```
void ShowMessage(Queue<MsgInnerInfo> qLinkButtionMsgInfo, string msg, MessageBoxOptions options, Action<MessageBoxResult> action, string title = "", MessageBoxType msgType = MessageBoxType.Notice);
```






