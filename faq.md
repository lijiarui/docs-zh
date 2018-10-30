# FAQ

## 1. 无法登陆

### 1.1 我的微信号无法登陆

从2017年6月下旬开始，使用基于web版微信接入方案存在大概率的被限制登陆的可能性。 主要表现为：无法登陆Web 微信，但不影响手机等其他平台。 验证是否被限制登陆： [https://wx.qq.com](https://wx.qq.com) 上扫码查看是否能登陆。 更多内容详见：

* [Can not login with error message: 当前登录环境异常。为了你的帐号安全，暂时不能登录web微信。](https://github.com/Chatie/wechaty/issues/603)
* [\[谣言\] 微信将会关闭网页版本](https://github.com/Chatie/wechaty/issues/990)
* [新注册的微信号无法登陆](https://github.com/Chatie/wechaty/issues/872)
* [wechaty-puppet-puppeteer](https://github.com/chatie/wechaty-puppet-puppeteer)

{% hint style="success" %}
**解决方案： 我们提供了非web 版本解决方案，**[**点击购买token**](https://github.com/lijiarui/wechaty-puppet-padchat/wiki/%E8%B4%AD%E4%B9%B0token) **, 更多技术细节查看** [**wechaty-puppet-padchat**](https://github.com/lijiarui/wechaty-puppet-padchat)
{% endhint %}

## 2. 功能相关

Tips： 请先看 Puppet 兼容性，再进行提问。

### 2.1 支持 红包、转账、朋友圈… 吗？

以下功能目前均不支持

- 支付相关 - 红包、转账、收款 等都不支持
- 在群聊中@他人 - 是的，Web 微信中被人@后也不会提醒
- 朋友圈相关 - 后续会支持

以下功能部分支持
- 发送分享链接，仅padchat 支持
- 发送名片，仅padchat 支持
- 发送语音消息，仅padchat 支持

### 2.2 wechaty 是支持个人号还是公众号？
现阶段，wechaty 只支持个人号

相关Issue:
- [Using wechaty to start a wechatOA account](https://github.com/Chatie/wechaty/issues/1016)

### 2.3 wechaty 是否可以发送卡片消息，然后跳转到网页

PuppetPadchat 是支持的， 其他版本是不支持的。
更多功能清单请参考： 

## 3. 最佳实践

### 3.1 wechaty & 队列的最佳实践

为了防止微信封号，wechaty 内置了队列，详细可见：[rx-queue](https://github.com/zixia/rx-queue)

### 3.2 如何能不多次扫码登陆机器人

在启动的时候可以设置wechaty 的 name（旧版本叫profile） 来存储机器人的登陆信息，登陆后会自动生成一个`*.memory-card.json` 的文件，这样再次运行的时候，就不需要扫码就可以直接登陆机器人了

```typescript
const bot = Wechaty.instance({ profile: 'your-cute-bot-name' })
```

### 3.3 我发现在根目录下有一个`default.memory-card.json` 的文件，这个文件是干什么的？

`default.memory-card.json` 会用来存储登陆信息，机器人可以通过这个文件实现自动登陆。

### 3.4 既然`default.memory-card.json` 存储了机器人的登陆信息，如果我想启动多个机器人，如何防止每次启动的时候加载不同的信息呢？

如果你想在一个机器上启动多个机器人，你可以通过设置 name（旧版本叫profile） 的值设置不同的机器人登陆信息，对应的你得到多个`*.memory-card.json`文件。有两种方法可以设置profile

**1. wechaty 初始化的时候设置profile**
```typescript
const bot = Wechaty.instance({ profile: 'your-cute-bot-name' })
```
**2. 通过设置`WECHATY_PROFILE` 环境变量传递profile**
```shell
WECHATY_PROFILE="your-cute-bot-name" node bot.js
```

这样，你就可以在根目录下看到`your-cute-bot-name.memory-card.json`的文件了。


## 4. 其他

### 4.1 wechaty 和 wechat4u 项目，有什么区别？
wechaty 可以实现多个微信接入的方案，对外提供统一的接口，包括web，ipad，ios等等，其中[wechat4u](https://github.com/nodeWechat/wechat4u) 是[SPACELAN](https://github.com/spacelan)写的基于web 实现微信接入的，wechaty 可以实现用wechaty 的接口，调用wechat4u的api。

> 这么理解：wechat4u有的，wechaty都有，反之不一定有，对么？

这个也不是完全确定的，因为wechaty 只是基于wechaty 暴露出来的接口为wechat4u 进行了封装

如果FAQ的内容无法满足你，可以点击链接发issue：
