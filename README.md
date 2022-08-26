# [WIP] LUFFA 丝瓜

借助各种开源组件创建一个易于搭建、配置和使用的开源工作流框架。

## 组件

| 组件           | 开源方案                       |
| -------------- | ------------------------------ |
| 电子邮件       | postfix dovecot rspamd         |
| 用户中心       | Casdoor / OpenLDAP / freeIPA   |
| OAuth2         | Spring Authorization Server    |
| 项目管理       | Redmine                        |
| 知识库         | MediaWiki                      |
| 版本仓库       | Gitea                          |
| 流水线         | Jenkins                        |
| Maven仓库      | Nexus                          |
| Docker镜像仓库 | Harbor                         |
| 监控           | prometheus alertmanager grafna |
| 日志           | ELK                            |

## 部署方式

任何一个广泛传播的开源项目都会支持从简单到支持客制化的多种部署方式。对于没有容器环境的用户来说使用安装脚本是一种最基本的部署方式；而对于习惯使用容器环境的用户来说docker-compose将是一种快速开始的方式；当然，对于计划长期将该框架作为流水线使用的用户来说，使用kubernetes才是最好的部署方式。

除了上面提到的安装方式，使用安装工具实现自动化安装和管理将是一种更进阶的部署方式，而这个工具将支持本地运行和容器化部署两种方式。

1. shell
2. docker-compose
3. helm
4. 安装工具

## 快速开始

### 使用 Docker Compose

启动服务

```bash
cd compose
# 使用 docker-compose 命令
docker-compose up -d
# 或者使用 docker 集成的 compose 命令
docker compose up -d
```

### 准备工作

## 更多文档

1. [身份提供者](./docs/AuthenticationProvider.md)
2. [CICD](./docs/CICD.md)