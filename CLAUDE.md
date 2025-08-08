# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是greatestofalltime.ton的极简静态个人网站项目，展示"我是最强的区块链天才！！！！！"。主要通过GitHub Pages部署，也支持作为TON Site运行。

## 关键命令

### GitHub Pages部署（推荐）
```bash
# 1. 创建GitHub仓库并上传代码
# 2. 在仓库设置中启用GitHub Pages，选择"GitHub Actions"作为源
# 3. 每次推送到main分支会自动部署
```

### 本地开发和测试
```bash
# 可以直接在浏览器中打开index.html预览
# 或使用简单的HTTP服务器
python3 -m http.server 8000
# 然后在浏览器访问 http://localhost:8000
```

### Docker部署（高级用户）
```bash
# 启动Caddy服务器
docker compose up --build -d

# 停止服务
docker compose down

# 重定向模式（取消注释docker-compose.yml中的重定向配置行并重启）
docker compose up --build -d
```

### TON Site部署
```bash
# 下载TON reverse-proxy
wget -O tonutils-reverse-proxy https://github.com/ton-utils/reverse-proxy/releases/latest/download/tonutils-reverse-proxy-linux-arm64
chmod +x tonutils-reverse-proxy

# 首次运行reverse proxy（获取配置并通过QR码批准交易）
./tonutils-reverse-proxy --domain greatestofalltime.ton

# 编辑config.json设置代理
sudo vim config.json
# set "proxy_pass": "http://127.0.0.1:12169/"

# 以守护进程模式运行TON reverse-proxy
./tonutils-reverse-proxy --domain greatestofalltime.ton &

# 停止TON reverse-proxy
ps aux | grep tonutils-reverse-proxy
kill -9 XXX
```

## 项目架构

### 核心文件结构
- `index.html` - 主页面，极简设计，居中显示主要标语
- `.github/workflows/deploy.yml` - GitHub Actions自动部署配置
- `docker-compose.yml` - Docker配置，运行Caddy服务器在端口12169（可选）
- `Caddyfile` - Caddy配置，提供静态文件服务（可选）
- `Caddyfile.redirect` - 重定向配置，重定向到karfly.github.io（可自定义）
- `favicon.ico` - 网站图标

### 技术栈
- **前端**: 纯HTML/CSS，响应式设计
- **服务器**: Caddy（通过Docker运行）
- **部署**: Docker Compose + TON reverse-proxy支持
- **样式**: 内联CSS，单色调设计，支持移动端

### 设计特点
- 极简主义设计，黑白配色
- 等宽字体（Lucida Console）
- 响应式布局，移动端优化
- 居中对齐的大标题设计
- 支持多种屏幕尺寸

## 内容更新
页面内容硬编码在index.html中，主要内容为"我是最强的区块链天才！！！！！"。如需修改文本内容，直接编辑index.html文件中的.main-message元素即可。

## 部署模式
1. **GitHub Pages模式**（推荐）: 通过GitHub Actions自动部署到GitHub Pages
2. **Docker标准模式**: 直接提供静态文件服务
3. **Docker重定向模式**: 重定向所有请求到指定URL
4. **TON Site模式**: 通过TON网络访问（greatestofalltime.ton域名）

## TON域名连接
- **简单方式**: 在TON DNS中将域名重定向到GitHub Pages URL
- **高级方式**: 使用TON reverse-proxy连接到本地Docker服务