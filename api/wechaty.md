---
description: Wechaty 是主要的bot 类，一个 Bot 代表着一个微信客户端。
---

# Wechaty

根据你选择的[Puppet](../puppet.md)的不同，Bot 可能等于下面中的一个客户端，不同的[Puppet](https://github.com/Chatie/wechaty/wiki/Puppet) 代表的我们对微信协议的不同实现方式, Puppet的英文意思是`傀儡`, 很形象的描述了我们希望Puppet做的事情：帮助 Wechaty 来控制微信的操作。

* 网页微信客户端, 当你选择: [puppet-puppeteer](https://github.com/chatie/wechaty-puppet-puppeteer)/[puppet-wechat4u](https://github.com/chatie/wechaty-puppet-wechat4u)​
* iPad 微信客户端, 当你选择: [puppet-padchat](https://github.com/lijiarui/wechaty-puppet-padchat)​

了解更多:

* [Wechaty 中的Puppet 是什么意思](../puppet.md#1-jie-shao)

如果你希望先了解如何发送消息，点击下面

{% page-ref page="message.md" %}

如果你希望先了解如何操作微信联系人，点击下面

{% page-ref page="contact.md" %}

如果你希望先了解如何操作微信群，点击下面

{% page-ref page="room.md" %}

## 类型定义

### [PuppetModuleName](#puppetmodulename​)

PuppetModuleName 参数在这里代表着Puppet 的名称，类型是 string, 可能的取值为：

- PUPPET_DEFAULT
- wechaty-puppet-ioscat'    
- wechaty-puppet-mock'      
- wechaty-puppet-padchat'   
- wechaty-puppet-padpro'    
- wechaty-puppet-puppeteer' 
- wechaty-puppet-wechat4u'  


### [WechatyOptions](#wechatyoptions)

这个参数

```ts
export interface WechatyOptions {
  memory?        : MemoryCard,
  name?          : string,                    // Wechaty Name
  profile?       : null | string,             // DEPRECATED: use name instead
  puppet?        : PuppetModuleName | Puppet, // Puppet name or instance
  puppetOptions? : PuppetOptions,             // Puppet TOKEN
  ioToken?       : string,                    // Io TOKEN
}
```

The option parameter to create a wechaty instance[WechatyEventName](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#WechatyEventName)​

Wechaty Class Event Type[WechatyEventFunction](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#WechatyEventFunction)​

Wechaty Class Event Function

## Wechaty <a id="wechaty"></a>

Main bot class.

A `Bot` is a wechat client depends on which puppet you use. It may equals

* web-wechat, when you use: [puppet-puppeteer](https://github.com/chatie/wechaty-puppet-puppeteer)/[puppet-wechat4u](https://github.com/chatie/wechaty-puppet-wechat4u)​
* ipad-wechat, when you use: [puppet-padchat](https://github.com/lijiarui/wechaty-puppet-padchat)​
* ios-wechat, when you use: puppet-ioscat

See more:

* ​[What is a Puppet in Wechaty](https://github.com/Chatie/wechaty-getting-started/wiki/FAQ-EN#31-what-is-a-puppet-in-wechaty)​

> If you want to know how to send message, see [Message](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Message) If you want to know how to get contact, see [Contact](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Contact)​

**Kind**: global class

* ​[Wechaty](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty)​
  * ​[new Wechaty\(\[options\]\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#new_Wechaty_new)​
  * _instance_
    * ​[.on\(event, listener\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty+on) ⇒ [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty)​
    * ​[.start\(\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty+start) ⇒ `Promise.`
    * ​[.stop\(\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty+stop) ⇒ `Promise.`
    * ​[.logout\(\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty+logout) ⇒ `Promise.`
    * ​[.logonoff\(\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty+logonoff) ⇒ `boolean`
    * ​[.userSelf\(\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty+userSelf) ⇒ `ContactSelf`
    * ​[.say\(textOrContactOrFileOrUrl\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty+say) ⇒ `Promise.`
  * _static_
    * ​[.instance\(\[options\]\)](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty.instance)​

### new Wechaty\(\[options\]\) <a id="new-wechaty-options"></a>

Creates an instance of Wechaty.

| Param | Type | Default |
| :--- | :--- | :--- |
| \[options\] | ​[`WechatyOptions`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#WechatyOptions)​ | `{}` |

**Example** _\(The World's Shortest ChatBot Code: 6 lines of JavaScript\)_

```text
const { Wechaty } = require('wechaty')const bot = new Wechaty()bot.on('scan',    (qrcode, status) => console.log(['https://api.qrserver.com/v1/create-qr-code/?data=',encodeURIComponent(qrcode),'&size=220x220&margin=20',].join('')))bot.on('login',   user => console.log(`User ${user} logined`))bot.on('message', message => console.log(`Message: ${message}`))bot.start()
```

### wechaty.on\(event, listener\) ⇒ [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty)​ <a id="wechaty-on-event-listener-wechaty"></a>

When the bot get message, it will emit the following Event.

You can do anything you want when in these events functions. The main Event name as follows:

* **scan**: Emit when the bot needs to show you a QR Code for scanning. After scan the qrcode, you can login
* **login**: Emit when bot login full successful.
* **logout**: Emit when bot detected log out.
* **message**: Emit when there's a new message.

see more in [WechatyEventName](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#WechatyEventName)​

**Kind**: instance method of [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty) **Returns**: [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty) - - this for chaining, see advanced [chaining usage](https://github.com/Chatie/wechaty-getting-started/wiki/FAQ-EN#36-why-wechatyonevent-listener-return-wechaty)​

| Param | Type | Description |
| :--- | :--- | :--- |
| event | ​[`WechatyEventName`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#WechatyEventName)​ | Emit WechatyEvent |
| listener | ​[`WechatyEventFunction`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#WechatyEventFunction)​ | Depends on the WechatyEvent |

**Example** _\(Event:scan\)_

```text
// Scan Event will emit when the bot needs to show you a QR Code for scanning​bot.on('scan', (url, code) => {  console.log(`[${code}] Scan ${url} to login.` )})
```

**Example** _\(Event:login \)_

```text
// Login Event will emit when bot login full successful.​bot.on('login', (user) => {  console.log(`user ${user} login`)})
```

**Example** _\(Event:logout \)_

```text
// Logout Event will emit when bot detected log out.​bot.on('logout', (user) => {  console.log(`user ${user} logout`)})
```

**Example** _\(Event:message \)_

```text
// Message Event will emit when there's a new message.​wechaty.on('message', (message) => {  console.log(`message ${message} received`)})
```

**Example** _\(Event:friendship \)_

```text
// Friendship Event will emit when got a new friend request, or friendship is confirmed.​bot.on('friendship', (friendship) => {  if(friendship.type() === Friendship.Type.Receive){ // 1. receive new friendship request from new contact    const contact = friendship.contact()    let result = await friendship.accept()      if(result){        console.log(`Request from ${contact.name()} is accept succesfully!`)      } else{        console.log(`Request from ${contact.name()} failed to accept!`)      }      } else if (friendship.type() === Friendship.Type.Confirm) { // 2. confirm friendship      console.log(`new friendship confirmed with ${contact.name()}`)   } })
```

**Example** _\(Event:room-join \)_

```text
// room-join Event will emit when someone join the room.​bot.on('room-join', (room, inviteeList, inviter) => {  const nameList = inviteeList.map(c => c.name()).join(',')  console.log(`Room ${room.topic()} got new member ${nameList}, invited by ${inviter}`)})
```

**Example** _\(Event:room-leave \)_

```text
// room-leave Event will emit when someone leave the room.​bot.on('room-leave', (room, leaverList) => {  const nameList = leaverList.map(c => c.name()).join(',')  console.log(`Room ${room.topic()} lost member ${nameList}`)})
```

**Example** _\(Event:room-topic \)_

```text
// room-topic Event will emit when someone change the room's topic.​bot.on('room-topic', (room, topic, oldTopic, changer) => {  console.log(`Room ${room.topic()} topic changed from ${oldTopic} to ${topic} by ${changer.name()}`)})
```

**Example** _\(Event:room-invite, RoomInvitation has been encapsulated as a RoomInvitation Class. \)_

```text
// room-invite Event will emit when there's an room invitation.​bot.on('room-invite', async roomInvitation => {  try {    console.log(`received room-invite event.`)    await roomInvitation.accept()  } catch (e) {    console.error(e)  }}
```

**Example** _\(Event:error \)_

```text
// error Event will emit when there's an error occurred.​bot.on('error', (error) => {  console.error(error)})
```

### wechaty.start\(\) ⇒ `Promise.` <a id="wechaty-start-promise"></a>

When you start the bot, bot will begin to login, need you wechat scan qrcode to login

> Tips: All the bot operation needs to be triggered after start\(\) is done

**Kind**: instance method of [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty) **Example**

```text
await bot.start()// do other stuff with bot here
```

### wechaty.stop\(\) ⇒ `Promise.` <a id="wechaty-stop-promise"></a>

Stop the bot

**Kind**: instance method of [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty) **Example**

```text
await bot.stop()
```

### wechaty.logout\(\) ⇒ `Promise.` <a id="wechaty-logout-promise"></a>

Logout the bot

**Kind**: instance method of [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty) **Example**

```text
await bot.logout()
```

### wechaty.logonoff\(\) ⇒ `boolean` <a id="wechaty-logonoff-boolean"></a>

Get the logon / logoff state

**Kind**: instance method of [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty) **Example**

```text
if (bot.logonoff()) {  console.log('Bot logined')} else {  console.log('Bot not logined')}
```

### wechaty.userSelf\(\) ⇒ `ContactSelf` <a id="wechaty-userself-contactself"></a>

Get current user

**Kind**: instance method of [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty) **Example**

```text
const contact = bot.userSelf()console.log(`Bot is ${contact.name()}`)
```

### wechaty.say\(textOrContactOrFileOrUrl\) ⇒ `Promise.` <a id="wechaty-say-textorcontactorfileorurl-promise"></a>

Send message to userSelf, in other words, bot send message to itself.

> Tips: This function is depending on the Puppet Implementation, see [puppet-compatible-table](https://github.com/Chatie/wechaty/wiki/Puppet#3-puppet-compatible-table)​

**Kind**: instance method of [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty)​

| Param | Type | Description |
| :--- | :--- | :--- |
| textOrContactOrFileOrUrl | `string` \| `Contact` \| `FileBox` | send text, Contact, or file to bot. &lt;/br&gt; You can use [FileBox](https://www.npmjs.com/package/file-box) to send file |

**Example**

```text
const bot = new Wechaty()await bot.start()// after logged in​// 1. send text to bot itselfawait bot.say('hello!')​// 2. send Contact to bot itselfconst contact = bot.Contact.load('contactId')await bot.say(contact)​// 3. send Image to bot itself from remote urlimport { FileBox }  from 'file-box'const fileBox = FileBox.fromUrl('https://chatie.io/wechaty/images/bot-qr-code.png')await bot.say(fileBox)​// 4. send Image to bot itself from local fileimport { FileBox }  from 'file-box'const fileBox = FileBox.fromFile('/tmp/text.jpg')await bot.say(fileBox)
```

### Wechaty.instance\(\[options\]\) <a id="wechaty-instance-options"></a>

Get the global instance of Wechaty

**Kind**: static method of [`Wechaty`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#Wechaty)​

| Param | Type | Default |
| :--- | :--- | :--- |
| \[options\] | ​[`WechatyOptions`](https://docs.chatie.io/~/revisions/-LQ4xhAwjZxF8y32AG4S/wechaty/api/wechaty#WechatyOptions)​ | `{}` |

**Example** _\(The World's Shortest ChatBot Code: 6 lines of JavaScript\)_

```text
const { Wechaty } = require('wechaty')​Wechaty.instance() // Global instance.on('scan', (url, code) => console.log(`Scan QR Code to login: ${code}\n${url}`)).on('login',       user => console.log(`User ${user} logined`)).on('message',  message => console.log(`Message: ${message}`)).start()
```

## PuppetName <a id="puppetname"></a>

The term [Puppet](https://github.com/Chatie/wechaty/wiki/Puppet) in Wechaty is an Abstract Class for implementing protocol plugins. The plugins are the component that helps Wechaty to control the Wechat\(that's the reason we call it puppet\). The plugins are named XXXPuppet, for example:

* ​[PuppetPuppeteer](https://github.com/Chatie/wechaty-puppet-puppeteer):
* ​[PuppetPadchat](https://github.com/lijiarui/wechaty-puppet-padchat)​

**Kind**: global typedef **Properties**

| Name | Type | Description |
| :--- | :--- | :--- |
| wechat4u | `string` | The default puppet, using the [wechat4u](https://github.com/nodeWechat/wechat4u) to control the [WeChat Web API](https://wx.qq.com/) via a chrome browser. |
| padchat | `string` | - Using the WebSocket protocol to connect with a Protocol Server for controlling the iPad Wechat program. |
| puppeteer | `string` | - Using the [google puppeteer](https://github.com/GoogleChrome/puppeteer) to control the [WeChat Web API](https://wx.qq.com/) via a chrome browser. |
| mock | `string` | - Using the mock data to mock wechat operation, just for test. |

## WechatyOptions <a id="wechatyoptions"></a>

The option parameter to create a wechaty instance

**Kind**: global typedef **Properties**

| Name | Type | Description |
| :--- | :--- | :--- |
| profile | `string` | Wechaty Name. &lt;/br&gt; When you set this: &lt;/br&gt; `new Wechaty({profile: 'wechatyName'})` &lt;/br&gt; it will generate a file called `wechatyName.memory-card.json`. &lt;/br&gt; This file stores the bot's login information. &lt;/br&gt; If the file is valid, the bot can auto login so you don't need to scan the qrcode to login again. &lt;/br&gt; Also, you can set the environment variable for `WECHATY_PROFILE` to set this value when you start. &lt;/br&gt; eg: `WECHATY_PROFILE="your-cute-bot-name" node bot.js` |
| puppet | `PuppetModuleName` \| `Puppet` | Puppet name or instance |
| puppetOptions | `Partial.` | Puppet TOKEN |
| ioToken | `string` | Io TOKEN |

## WechatyEventName <a id="wechatyeventname"></a>

Wechaty Class Event Type

**Kind**: global typedef **Properties**

| Name | Type | Description |
| :--- | :--- | :--- |
| error | `string` | When the bot get error, there will be a Wechaty error event fired. |
| login | `string` | After the bot login full successful, the event login will be emitted, with a Contact of current logined user. |
| logout | `string` | Logout will be emitted when bot detected log out, with a Contact of the current login user. |
| heartbeat | `string` | Get bot's heartbeat. |
| friendship | `string` | When someone sends you a friend request, there will be a Wechaty friendship event fired. |
| message | `string` | Emit when there's a new message. |
| ready | `string` | Emit when all data has load completed, in wechaty-puppet-padchat, it means it has sync Contact and Room completed |
| room-join | `string` | Emit when anyone join any room. |
| room-topic | `string` | Get topic event, emitted when someone change room topic. |
| room-leave | `string` | Emit when anyone leave the room. |
| room-invite | `string` | Emit when there is a room invitation, see more in [RoomInvitation](https://github.com/Chatie/docs/tree/777195b62684a2fcb789911ad01bf3a16e5bdbf6/root/wechaty/api/RoomInvitation/README.md) If someone leaves the room by themselves, wechat will not notice other people in the room, so the bot will never get the "leave" event. |
| scan | `string` | A scan event will be emitted when the bot needs to show you a QR Code for scanning. &lt;/br&gt; It is recommend to install qrcode-terminal\(run `npm install qrcode-terminal`\) in order to show qrcode in the terminal. |

## WechatyEventFunction <a id="wechatyeventfunction"></a>

Wechaty Class Event Function

**Kind**: global typedef **Properties**

| Name | Type | Description |
| :--- | :--- | :--- |
| error | `function` | \(this: Wechaty, error: Error\) =&gt; void callback function |
| login | `function` | \(this: Wechaty, user: ContactSelf\)=&gt; void |
| logout | `function` | \(this: Wechaty, user: ContactSelf\) =&gt; void |
| scan | `function` | \(this: Wechaty, url: string, code: number\) =&gt; void |
| heartbeat | `function` | \(this: Wechaty, data: any\) =&gt; void |
| friendship | `function` | \(this: Wechaty, friendship: Friendship\) =&gt; void |
| message | `function` | \(this: Wechaty, message: Message\) =&gt; void |
| ready | `function` | \(this: Wechaty\) =&gt; void |
| room-join | `function` | \(this: Wechaty, room: Room, inviteeList: Contact\[\], inviter: Contact\) =&gt; void |
| room-topic | `function` | \(this: Wechaty, room: Room, newTopic: string, oldTopic: string, changer: Contact\) =&gt; void |
| room-leave | `function` | \(this: Wechaty, room: Room, leaverList: Contact\[\]\) =&gt; void |
| room-invite | `function` | \(this: Wechaty, room: Room, leaverList: Contact\[\]\) =&gt; void see more in [RoomInvitation](https://github.com/Chatie/docs/tree/777195b62684a2fcb789911ad01bf3a16e5bdbf6/root/wechaty/api/RoomInvitation/README.md)​ |

