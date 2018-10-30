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

| Wechaty Puppet                                                         | Backend Protocol            | Npm Name                 | Npm Version                                                               | Stage   |
| :----------------------------------------------------------------------| :---------------------------| :------------------------| :-------------------------------------------------------------------------| :-------|
| [PuppetPuppeteer](https://github.com/Chatie/wechaty-puppet-puppeteer)  | Web API via Browser Hooking | wechaty-puppet-puppeteer | ![PuppetPuppeteer](https://badge.fury.io/js/wechaty-puppet-puppeteer.svg)<br />[![npm (tag)](https://img.shields.io/npm/v/wechaty-puppet-puppeteer/next.svg)](https://www.npmjs.com/package/wechaty-puppet-puppeteer?activeTab=versions) | ![Stage:Release](https://img.shields.io/badge/Stage-Release-green.svg)  |
| [PuppetPadchat](https://github.com/lijiarui/wechaty-puppet-padchat)    | iPad Protocol               | wechaty-puppet-padchat   | ![PuppetPadchat](https://badge.fury.io/js/wechaty-puppet-padchat.svg) <br /> [![npm (tag)](https://img.shields.io/npm/v/wechaty-puppet-padchat/next.svg)](https://www.npmjs.com/package/wechaty-puppet-padchat?activeTab=versions)    | ![Stage:Release](https://img.shields.io/badge/Stage-Release-green.svg)    |
| [PuppetWechat4u](https://github.com/Chatie/wechaty-puppet-wechat4u)    | Web API via HTTP            | wechaty-puppet-wechat4u  | ![PuppetWechat4u](https://badge.fury.io/js/wechaty-puppet-wechat4u.svg) <br /> [![npm (tag)](https://img.shields.io/npm/v/wechaty-puppet-wechat4u/next.svg)](https://www.npmjs.com/package/wechaty-puppet-wechat4u?activeTab=versions)  | ![Stage:Release](https://img.shields.io/badge/Stage-Alpha-red.svg)      |
| [PuppetIoscat](https://github.com/linyimin-bupt/wechaty-puppet-ioscat) | iPhone App Hooking          | wechaty-puppet-ioscat    | ![PuppetIoscat](https://badge.fury.io/js/wechaty-puppet-ioscat.svg) <br /> [![npm (tag)](https://img.shields.io/npm/v/wechaty-puppet-ioscat/next.svg)](https://www.npmjs.com/package/wechaty-puppet-ioscat?activeTab=versions)      | ![Stage:Release](https://img.shields.io/badge/Stage-Alpha-red.svg)      |
| TBW                                                                    | Android Hook                | Android                  | 0.0.0                                                                     | ![Stage:Release](https://img.shields.io/badge/Stage-Plan-lightgrey.svg) |
| TBW                                                                    | Win32 Hook                  | Win32                    | 0.0.0                                                                     | ![Stage:Release](https://img.shields.io/badge/Stage-Plan-lightgrey.svg) |

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

| Wechaty Puppet                                              | Backend Protocol    | Npm Name            |  Npm Version                                                    | Stage   |
| :-----------------------------------------------------------| :-------------------| :-------------------| :---------------------------------------------------------------| :-------|
| [Puppet](https://github.com/Chatie/wechaty-puppet)          | Abstract Base Class | wechaty-puppet      | ![Puppet](https://badge.fury.io/js/wechaty-puppet.svg) <br /> [![npm (tag)](https://img.shields.io/npm/v/wechaty-puppet/next.svg)](https://www.npmjs.com/package/wechaty-puppet?activeTab=versions)         | ![Stage:Release](https://img.shields.io/badge/Stage-Release-green.svg) |
| [PuppetMock](https://github.com/Chatie/wechaty-puppet-mock) | Mocking             | wechaty-puppet-mock | ![PuppetMock](https://badge.fury.io/js/wechaty-puppet-mock.svg) <br /> [![npm (tag)](https://img.shields.io/npm/v/wechaty-puppet-mock/next.svg)](https://www.npmjs.com/package/wechaty-puppet-mock?activeTab=versions)| ![Stage:Release](https://img.shields.io/badge/Stage-Release-green.svg) |

## 3. Wechaty Puppet 兼容性

### 3.1 Puppet 联系人接口

| Contact API | wechat4u &<br />puppeteer | padchat | Ioscat
| --- | :---: | :---: | :---: |
| Permanent ContactPayload.id  | ~~No~~ | Yes | ~~No~~
| ContactPayload.friend | ~~No~~ | Yes | Yes

### 3.2 Puppet 消息收发接口

| Message API | wechat4u &<br />puppeteer | padchat | Ioscat
| --- | :---: | :---: | :---: |
| messageSendContact() | ~~No~~ | Yes | ~~No~~
| messageFile() | Yes | Yes for Image/Audio/Video<br />No for other Attachments | ~~No~~
| messageSendFile() | Yes | Yes for Image/Audio/Video<br />No for other Attachments | ~~No~~ |
| messageSendUrl() | ~~No~~ | Yes | ~~No~~ |

### 3.3 Puppet 微信群接口

| Room API | wechat4u &<br />puppeteer | padchat | Ioscat
| --- | :---: | :---: | :---: |
| Permanent RoomPayload.id | ~~No~~ | Yes | ~~No~~
| roomQrcode() | ~~No~~ | Yes | Yes
| roomCreate() | ~~No~~ | Yes | Yes
| roomAdd() | ~~No~~ | Yes | Yes
| roomDel() | ~~No~~ | Yes | Yes
| roomQuit() | ~~No~~ | Yes | Yes
| roomAnnounce() | ~~No~~ | Yes | Yes
| roomPayload.owner | ~~No~~ | Yes | ~~No~~

## 4. 了解更多

你可以参考这里了解更多的 Wechaty Puppet 内容： [https://github.com/Chatie/wechaty-puppet/wiki](https://github.com/Chatie/wechaty-puppet/wiki)

* Github: [https://github.com/Chatie/wechaty-puppet](https://github.com/Chatie/wechaty-puppet)
* 文档说明: [https://chatie.io/wechaty-puppet/typedoc/classes/puppet.html](https://chatie.io/wechaty-puppet/typedoc/classes/puppet.html)
* Puppet 开发指南: [https://github.com/Chatie/wechaty-puppet/wiki/Development](https://github.com/Chatie/wechaty-puppet/wiki/Development)
* Puppet 相关链接: [https://github.com/Chatie/wechaty-puppet/wiki/Links](https://github.com/Chatie/wechaty-puppet/wiki/Links)

