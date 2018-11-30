# 最佳实践

## 1. 规则

1. 使用TypeScript 作为开发语言，TypeScript 是强类型的JavaScript，统一typings，增强系统的可维护性。更多请查看issue 讨论：[\#1066](https://github.com/Chatie/wechaty/issues/1066), [\#1064](https://github.com/Chatie/wechaty/issues/1064).
2. 使用TSLint 作为代码检查工具，为什么需要？[推荐阅读这个了解详情](https://ts.xcatliu.com/engineering/lint.html)。wechaty 的tslint 配置说明请参考[这篇博客](https://blog.chatie.io/migrating-wechaty-v0.14-to-v0.18-guide-from-puppeteer-to-padchat-zh/)。
3. 使用 [VSCode](https://code.visualstudio.com/) 作为编译器。
4. 文件的命名规则是小写，用`-` 连接所有的内容而不是空格。比如`2017-10-06-wechat-pc-impactor` 而不是 `2017-10-06-WeChat PC Impactor`
5. 变量命名为`小驼峰`写法。如 `userName` 而不是 `user_name`。

## 2. 机器人启动方法

```typescript
import { PuppetPadchat } from 'wechaty-puppet-padchat'
const puppet = new PuppetPadchat()
const bot = new Wechaty({ 
    puppet,
    name: 'your-bot-name'
})
```

## 3. 保存机器人登陆信息

## 4. 日志调试

## 5. 推荐版本

## 6. 环境要求

## 7. 代码示例

