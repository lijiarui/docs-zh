# Puppet

## 1. 介绍

不同的[Puppet](https://github.com/Chatie/wechaty/wiki/Puppet) 代表的我们对微信协议的不同实现方式, Puppet的英文意思是`傀儡`, 很形象的描述了我们希望Puppet做的事情：帮助 Wechaty 来控制微信的操作。

所有的实现方式都以`PuppetXXX` 来命名的，比如[PuppetPuppeteer](https://github.com/Chatie/wechaty-puppet-puppeteer) 是通过谷歌浏览器，通过 [google puppeteer](https://github.com/GoogleChrome/puppeteer)来控制[网页微信API](https://wx.qq.com)。[PuppetPadchat](https://github.com/lijiarui/wechaty-puppet-padchat) 是通过WebSocket 连接一个协议服务器来控制iPad 微信。

如果你希望深入了解Puppet是如何在Wechaty 运行的，你可以在[https://github.com/Chatie/wechaty-puppet/blob/master/src/puppet.ts](https://github.com/Chatie/wechaty-puppet/blob/master/src/puppet.ts) 查看源代码。

基于网页微信的实现方式是免费的，基于其他的接入方式是收费的，详细介绍：[收费说明](https://github.com/lijiarui/wechaty-puppet-padchat/wiki/购买token)

以下是Puppet 和Wechaty 的架构图，更多Puppet 的介绍在这里： [Puppet in wiki](https://github.com/Chatie/wechaty-puppet/wiki)

![](https://github.com/Chatie/wechaty/wiki/image/abstract-info.png)

## 2. Wechaty Puppet 清单

### 2.1 调用 Wechaty 的开发者

| Puppet | 使用的微信协议 | Npm 名称 | Npm 版本 | 状态 |
| :--- | :--- | :--- | :--- | :--- |
|  | 通过浏览器Hook 网页API |  |  |  |
|  | iPad 协议 |  |  |  |
|  | 通过HTTP 调用网页API |  |  |  |
|  | iPhone Hook |  |  |  |
|  | Android Hook |  |  |  |
|  | Win32 Hook |  |  |  |

### 2.2 开发 Puppet 开发者

| Puppet | 使用的微信协议 | Npm 名称 | Npm 版本 | 状态 |
| :--- | :--- | :--- | :--- | :--- |
|  | 抽象父类 |  |  |  |
|  | 为单元测试提供模拟调用 |  |  |  |

## 3. Wechaty Puppet 兼容性

### 3.1 Puppet 联系人接口

### 3.2 Puppet 消息收发接口

### 3.3 Puppet 微信群接口

## 4. 了解更多

你可以参考这里了解更多的 Wechaty Puppet 内容： [https://github.com/Chatie/wechaty-puppet/wiki](https://github.com/Chatie/wechaty-puppet/wiki)

* Github: [https://github.com/Chatie/wechaty-puppet](https://github.com/Chatie/wechaty-puppet)
* 文档说明: [https://chatie.io/wechaty-puppet/typedoc/classes/puppet.html](https://chatie.io/wechaty-puppet/typedoc/classes/puppet.html)
* Puppet 开发指南: [https://github.com/Chatie/wechaty-puppet/wiki/Development](https://github.com/Chatie/wechaty-puppet/wiki/Development)
* Puppet 相关链接: [https://github.com/Chatie/wechaty-puppet/wiki/Links](https://github.com/Chatie/wechaty-puppet/wiki/Links)

