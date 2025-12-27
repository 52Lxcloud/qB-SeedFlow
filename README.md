<div align="center">
  <img src="assets/icon.webp" alt="SeedFlow Icon" width="120" />

  # SeedFlow

  **高效管理 qBittorrent 客户端，支持限速、打标签和 Docker 部署**

  <p>
    <img src="https://img.shields.io/docker/v/52lxcloud/seedflow?logo=docker" alt="Docker Version">
    <img src="https://img.shields.io/docker/pulls/52lxcloud/seedflow?logo=docker" alt="Docker Pulls">
  </p>

  <p>
    <a href="https://www.lxink.cn/posts/share/seedflow">完整教程</a> • 
    <a href="#功能特性">功能特性</a> • 
    <a href="#快速开始">快速开始</a> • 
    <a href="#环境变量">环境变量</a> • 
    <a href="#联系我">联系我</a>
  </p>
</div>

## 功能特性

- 多 qBittorrent 客户端管理
- 按标签/分类/名称/Tracker 设置限速规则
- 自动打标签（根据 Tracker 域名）
- 被控端一键安装
- 实时心跳监控与日志查看

## 快速开始

> 如果你是初次使用，建议阅读 [**完整图文教程**](https://www.lxink.cn/posts/share/seedflow) 

### Docker Compose（推荐）

```yaml
version: '3.8'

services:
  seedflow:
    image: 52lxcloud/seedflow:latest
    container_name: seedflow
    ports:
      - "5427:5427"
    environment:
      - DEFAULT_PASSWORD=lxcloud
    volumes:
      - ./config:/app/config
    restart: unless-stopped

```

```bash
docker-compose pull && docker-compose up -d
```

### Docker Run

```bash
mkdir -p config
docker run -d \
  --name seedflow \
  -p 5427:5427 \
  -v ./config:/app/config \
  --restart unless-stopped \
  52lxcloud/seedflow:latest
```

访问 http://localhost:5427 默认密码：`lxcloud`

## 环境变量

| 变量 | 默认值 | 说明 |
|------|--------|------|
| DEFAULT_PASSWORD | lxcloud | 初始密码 |

## 被控端

标准版适用于4.6.0+（推荐）  
兼容版为通用版本，只建议用于4.6.0以下  

## 联系我

- TG频道: https://t.me/Lx_hub
