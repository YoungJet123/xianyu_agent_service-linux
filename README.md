# 闲鱼智能客服 RPA - Linux 版本

基于 [xinayu_agent_kefu](https://github.com/原作者/xinayu_agent_kefu) 移植到 Ubuntu/Linux 平台的版本，核心功能完全一致，针对 Linux 环境做了适配修复。

## 主要改动

- 修复 GUI 线程中 DISPLAY 环境变量未传递导致浏览器窗口无法弹出的问题
- 修复 VPN/系统代理导致 Coze API 连接失败的问题（httpx 添加 `trust_env=False`）
- 新增 Ubuntu 部署教程

## 功能简介

专为闲鱼小商家打造的 AI 智能客服系统，通过 RPA 自动读取和回复闲鱼消息，结合 Coze AI 工作流实现智能回复。

- 自动监控闲鱼消息，AI 决策后自动回复
- 消息合并：用户连发多条消息时合并理解后统一回复
- 跨会话记忆：记住老客户历史对话
- 主动触达：用户沉默后自动跟进
- 多模态：支持图片理解

## 环境要求

- Ubuntu 桌面版（已在 22.04 验证）
- Python 3.8+
- MySQL 5.7+

## 快速开始

详见 [Ubuntu部署教程.md](./Ubuntu部署教程.md)

## 配置

复制 `.env.example` 为 `.env` 并填写：

```
COZE_API_TOKEN=你的Coze API Token
COZE_BOT_ID=你的Bot ID
DB_PASSWORD=你的MySQL密码
DB_NAME=xbot
```

## 启动

```bash
python3 gui.py
```
