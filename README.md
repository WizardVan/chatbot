# ChatBot 聊天机器人

一个功能简单、稳定的聊天机器人.  
你可以通过该机器人接入一些有趣的 API 来实现一些好玩的应用,例如快递查询、毒鸡汤、斗图等,也可以把自己人接入自己的服务中,作为告警、定时通知等服务.

## 接入流程

![流程图](./images/flow.png)

> 图上蓝色部分都是你需要做的内容

## 具体步骤

1. 添加机器人为好友,一般在 1-2 分钟后会自动通过
2. 根据提示操作,可以发送`#帮助#`来获取具体指令,激活机器人
3. 编写代码,连接机器人的 WebSocket Server 用于接收推送消息
4. 编写 Http Client 的代码,用于请求机器人接口,让机器人发送消息给你

## HTTP 接口

> 服务器地址为 demo 里的 server 地址  
> 所有接口都为 POST,参数为 json 格式放在 body 中,token 拼接在 url 上  
> HEADER:Content-Type:application/json; charset=utf-8  
> 例子: http://服务器地址/api/v1/chat/sendText?token=your_token

#### 发送文本消息

URI: /api/v1/chat/sendText  
METHOD:`POST`  
参数:  
toUser string //接收人 username  
content string //发送的文本内容

#### 发送图片消息

URI: /api/v1/chat/sendPic  
METHOD:`POST`  
参数:  
toUser string //接收人 username  
imgUrl string //图片的网络地址

#### 发送表情/动图消息

URI: /api/v1/chat/sendEmoji  
METHOD:`POST`  
参数:  
toUser string //接收人 username  
gifUrl string //图片的网络地址

## DEMO

-   [ChatBot-Go](https://github.com/chatrbot/chatbot-go)
-   [ChatBot-Node](https://github.com/chatrbot/chatbot-node)
-   [ChatBot-PHP](https://github.com/chatrbot/chatbot-php)

## 功能

### 个人

-   [x] 机器人转发文本消息到 websocket 客户端
-   [x] 机器人发送文本类型消息
-   [x] 机器人发送图片类型消息
-   [x] 机器人发送表情类型消息

### 群聊

功能正在开发...

## 示例截图

![demo](./images/demo.png)

## FAQ

Q:如何获取 Token?  
A:加入技术交流群,添加群内机器人为好友,然后发送相关指令激活获取

## 联系方式

![qrcode_group](./images/qrcode_group.png)
