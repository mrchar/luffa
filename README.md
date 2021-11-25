# LUFFA 丝瓜

借助各种开源组件创建一个易于搭建、配置和使用的开源工作流框架。

## 组件

| 组件           | 开源方案 |
| -------------- | -------- |
| 用户中心       | OpenLDAP |
| 版本仓库       | Gitea    |
| 流水线         | Jenkins  |
| Maven仓库      | Nexus    |
| Docker镜像仓库 | Harbor   |

## 部署方式

任何一个广泛传播的开源项目都会支持从简单到支持客制化的多种部署方式。对于没有容器环境的用户来说使用安装脚本是一种最基本的部署方式；而对于习惯使用容器环境的用户来说docker-compose将是一种快捷的快速开始的方式；当然，对于计划长期将该框架作为流水线使用的用户来说，使用kubernetes才是最好的部署方式。

1. shell
2. docker-compose
3. helm

## 更多文档

[身份提供者](./docs/AuthenticationProvider.md)