---
abbrlink: 76ccdb2e
date: 2021-06-09
---
## 项目背景

原 2020 年**开源供应链点亮计划**有项目“基于开放 API 封装 Wechaty 接口下的飞书聊天机器人”。

原项目已实现**图片、群聊、附件、Ding**这些功能。

但其中 puppet 有部分接口没有完全实现功能。

现需要对接飞书接口，以完善 puppet 上各个类型的消息接口。

另外在实现 puppet 接口后，在 ding-dong-bot.ts 中增加对应的订阅消息事件。

## 方案描述

#### 功能

- [ ] 富文本
- [ ] 群名片
- [ ] 消息卡片
- [ ] 日历
- [ ] 会议室
- [ ] 视频会议
- [ ] 邮箱
- [ ] 打卡

#### 非功能

- [ ] 完善飞书 puppet 的使用文档

## 时间规划

- 熟悉技术栈
  - 7.1 - 7.15
  - 阅读 wechaty-puppet-lark 源代码，学习 TypeScript
- 完善富文本等功能对应的 puppet 接口
  - 7.15 - 8.7
  - 阅读飞书开放平台文档，熟悉飞书服务端 API
  - 完善飞书 puppet 的接口
- 完成富文本等功能对应的订阅事件
  - 8.7 - 8.15
  - 在 ding-dong-bot.ts 中增加相应的代码
- 重构代码
  - 8.15 - 8.23
- 完善飞书 puppet 使用文档
  - 8.22 - 8.30

## 参考资料

[飞书开放平台](https://open.feishu.cn/document/)
[wechaty-puppet-lark](https://github.com/wechaty/wechaty-puppet-lark)
[基于开放 API 封装 Wechaty 接口下的飞书聊天机器人：期初](https://wechaty.js.org/2020/07/29/wechaty-puppet-lark-plan-blog/)
[基于开放 API 封装 Wechaty 接口下的飞书聊天机器人：期中](https://wechaty.js.org/2020/08/19/wechaty-puppet-lark-mid-term-blog/)
[基于开放 API 封装 Wechaty 接口下的飞书聊天机器人：期末](https://wechaty.js.org/2020/09/30/wechaty-puppet-lark-final-blog/)
