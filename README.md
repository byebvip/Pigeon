# Pigeon
咕咕咕，咕咕咕咕咕？

一个轻量化的留言板 / 记事本 / 社交系统 / 博客，没有明确的作用定义，一切都随心所欲。


- 博客示例：https://tql.ink/


## 简介

你是否有些临时的想法，或者一小段代码，想找一个地方记下来？

用博客来存，感觉有点大材小用；用 txt 来存，又怕搞丢。

那么这就是一个很好的东西了，你可以把这些零零散散的内容记下来，而不会忘记。

> 你可以把它当成微博、推特，也可以当成在线聊天软件，或者是纯粹拿来写文章，写代码记事用。

## 特性

- 支持 Markdown 语法
- 支持公开、登录可见、仅自己可见三种类型
- 使用 BCRYPT 散列储存密码
- 支持邮件验证
- 支持 reCaptcha 验证码
- 支持 Timeline 时间线，可以查看任意时间以前的内容
- 消息动态刷新，实时查看最新消息
- 支持 highlight.js 代码语法高亮
- 支持一键更新系统程序
- 支持自定义页面模板
- 支持每条消息在单独页面显示
- 支持编辑已发布的消息

## 安装

Pigeon 的安装配置非常简单，只需要简单三行命令以及一些配置即可开始使用。

首先将项目拉取到本地

```
git clone https://github.com/kasuganosoras/Pigeon
```

然后

```
cd Pigeon/
php install.php
```

根据提示进行配置即可。

安装程序是没有界面的，请通过命令行执行 `install.php`，而不是通过网页访问它。

> 如需手动安装（不使用安装程序），请 [点击这里阅读安装方法](https://github.com/kasuganosoras/Pigeon/wiki/Install#%E6%89%8B%E5%8A%A8%E5%AE%89%E8%A3%85-pigeon)

## API
## 消息发布

Endpoint：`POST /?s=newpost&token=<你的 Token>`

POST 字段

| 字段     | 介绍     | 必须 | 可选值                                     |
| -------- | -------- | ---- | ------------------------------------------ |
| content  | 消息内容 | 是   | 无                                         |
| ispublic | 消息类型 | 是   | 0 所有人可见 / 1 登录后可见 / 2 仅自己可见 |

返回 `Successful`，错误会返回错误原因。

## 消息删除

Endpoint：`GET /?s=deletepost&id=<消息 ID>&token=<你的 Token>`

返回 `Successful`，错误会返回错误原因。

## 更改消息类型

Endpoint：`GET /?s=changepublic&id=<消息 ID>&newstatus=<新的消息类型>&token=<你的 Token>`

消息类型：0 所有人可见 / 1 登录后可见 / 2 仅自己可见


## 更改消息内容

我主要是加了这个功能;套了原命令

Endpoint：`POST /?s=xxgg&token=<你的 Token>&id=要修改的消息ID`

| 字段    | 介绍     | 必须 | 可选值 |
| ------- | -------- | ---- | ------ |
| content | 消息内容 | 是   | 无     |


## 关于 Admin Console

管理员后台的地址是：`/admin.php`

只有 root 和 admin 权限的用户可以访问管理员后台

您可以在管理员后台设置每个用户的信息，以及一键更新 Pigeon

## 开源协议

本项目使用 MIT 协议开源，可以用于商业使用

## 捐助原开发者

如果你觉得这个项目对你有帮助，欢迎赞助原作者

![img](https://i.imgur.com/1EuGD9o.png)
