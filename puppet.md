# Puppet

## 1. 介绍

不同的[Puppet](https://github.com/Chatie/wechaty/wiki/Puppet) 代表的我们对微信协议的不同实现方式, Puppet的英文意思是`傀儡`, 很形象的描述了我们希望Puppet做的事情：帮助 Wechaty 来控制微信的操作。

所有的实现方式都以`PuppetXXX` 来命名的，比如[PuppetPuppeteer](https://github.com/Chatie/wechaty-puppet-puppeteer) 是通过谷歌浏览器，通过 [google puppeteer](https://github.com/GoogleChrome/puppeteer)来控制[网页微信API](https://wx.qq.com)。[PuppetPadchat](https://github.com/lijiarui/wechaty-puppet-padchat) 是通过WebSocket 连接一个协议服务器来控制iPad 微信。

* 更多的Puppet 列表： 
* 不同的微信接入方式，功能清单是不一样的，不同接入方式的功能对比在这里： 

如果你希望深入了解Puppet是如何在Wechaty 运行的，你可以在[https://github.com/Chatie/wechaty-puppet/blob/master/src/puppet.ts](https://github.com/Chatie/wechaty-puppet/blob/master/src/puppet.ts) 查看源代码。

基于网页微信的实现方式是免费的，基于其他的接入方式是收费的，详细介绍：[收费说明](https://github.com/lijiarui/wechaty-puppet-padchat/wiki/购买token)

以下是Puppet 和Wechaty 的架构图，更多Puppet 的介绍在这里： [Puppet in wiki](https://github.com/Chatie/wechaty-puppet/wiki) 

![](https://github.com/Chatie/wechaty/wiki/image/abstract-info.png)

## 2. Wechaty Puppet 清单

### 2.1 面向 Puppet 用户(使用wechaty 接口的开发者)

### 2.2 面向 Puppet 创建者(深入开发 puppet 的开发者)

## 3. Wechaty Puppet 兼容性

### 3.1 Puppet Contact API

### 3.2 Puppet Message API

### 3.3 Puppet Room API

## 4. 了解更多

Learn more about Wechaty Puppet at <https://github.com/Chatie/wechaty-puppet/wiki>
- Repository: https://github.com/Chatie/wechaty-puppet
- Documentation: https://chatie.io/wechaty-puppet/typedoc/classes/puppet.html
- Puppet Development Guide: https://github.com/Chatie/wechaty-puppet/wiki/Development
- Puppet Related Links: https://github.com/Chatie/wechaty-puppet/wiki/Links