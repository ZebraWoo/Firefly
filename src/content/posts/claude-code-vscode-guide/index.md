---
title: Claude Code + VS Code 配置指南
published: 2026-06-06
description: '使用 deepseek-v4 模型配置 Claude Code，性价比拉满的 AI 编程方案'
tags: [Claude Code, VS Code, DeepSeek, AI编程]
category: 工具教程
draft: false
---

笔者还没想好博客的写作方向，先简单水一篇关于 Claude Code + VS Code 的配置指南(`・ω・´`)，为了降低上手难度，模型选择的是 **deepseek-v4**，性价比拉满~

## 一、下载 VS Code 插件

VS Code 插件栏搜索 `Claude Code for VS Code`，点击 Install。

![VS Code 插件安装](./images/Pasted%20image%2020260606170519.png)

## 二、购买 deepseek-v4 API

1. 搜索 "deepseek api"

   ![搜索 deepseek api](./images/Pasted%20image%2020260606170934.png)

2. 点击"API 开放平台"

   ![API 开放平台](./images/Pasted%20image%2020260606171011.png)

3. 点击充值，金额随意，可以充 10 块钱试试模型合不合适。

   ![充值页面](./images/Pasted%20image%2020260606171043.png)

4. 创建 API key，这里需要及时复制，key 不能二次查看，切莫轻易展示给他人。

   ![创建 API key](./images/Pasted%20image%2020260606171114.png)

## 三、VS Code 配置 deepseek-v4-flash 和 deepseek-v4-pro

1. `Ctrl+Shift+P`，输入 `open user settings(json)`

   ![打开用户设置](./images/Pasted%20image%2020260606171248.png)

2. 将配置代码复制进去

   ![粘贴配置代码](./images/Pasted%20image%2020260606171938.png)

配置代码如下：

```json
"claudeCode.preferredLocation": "sidebar",
"claudeCode.environmentVariables": [

    {
        "name": "ANTHROPIC_AUTH_TOKEN",
        "value": "sk-你创建的api key"
    },

    {
        "name": "ANTHROPIC_BASE_URL",
        "value": "https://api.deepseek.com/anthropic"
    },

    {
        "name": "ANTHROPIC_MODEL",
        "value": "deepseek-v4-pro[1m]"
    },

    {
        "name": "ANTHROPIC_DEFAULT_OPUS_MODEL",
        "value": "deepseek-v4-pro[1m]"
    },

    {
        "name": "ANTHROPIC_DEFAULT_SONNET_MODEL",
        "value": "deepseek-v4-pro[1m]"
    },

    {
        "name": "ANTHROPIC_DEFAULT_HAIKU_MODEL",
        "value": "deepseek-v4-flash"
    },

    {
        "name": "CLAUDE_CODE_SUBAGENT_MODEL",
        "value": "deepseek-v4-flash"
    },

    {
        "name": "CLAUDE_CODE_EFFORT_LEVEL",
        "value": "max"
    }
],
```

> **注意前后的 `,`，不然配置文件会报错！**

## 四、检查是否配置成功

1. 点击右上角 Claude Code 图标

   ![Claude Code 图标](./images/Pasted%20image%2020260606172653.png)

2. 询问它的模型内核

   ![询问模型内核](./images/Pasted%20image%2020260606172758.png)

恭喜你，可以开始 Vibe Coding 之旅啦！(´・ω・)つ旦
