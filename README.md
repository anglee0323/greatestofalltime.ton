# greatestofalltime.ton

一个极简个人网站，展示"我是最强的区块链天才！！！！！"

## 🚀 推荐：部署到TON Storage（完全去中心化，免费）

### 方式1: 使用推荐提供商部署（最便宜！）

**选定提供商**: 德国服务器 - 仅需 **0.50 TON**！
- 100%稳定，99.98%运行时间
- 通过 [mytonprovider.org](https://mytonprovider.org) 选定

**详细部署步骤**: 查看 [`TON-STORAGE-DEPLOY.md`](./TON-STORAGE-DEPLOY.md)

**快速部署**:
```bash
# 1. 下载工具
wget https://github.com/ton-blockchain/ton/releases/latest/download/storage-daemon-linux-x86_64
chmod +x storage-daemon-linux-x86_64

# 2. 启动daemon
./storage-daemon-linux-x86_64 -C storage-db -I 127.0.0.1:5555

# 3. 创建bag
storage-daemon-cli -I 127.0.0.1:5555 -k storage-db/cli-keys/client -p storage-db/cli-keys/server.pub
> create ton-storage-deploy/

# 4. 支付0.50 TON给提供商，获得Bag ID
# 5. 在dns.ton.org的"TON Storage"字段填入Bag ID
```

### 方式2: 使用TON Byte部署（如果可用）
1. 访问 [tonbyte.com](https://tonbyte.com)（注意：可能服务不稳定）
2. 创建账户并上传 `ton-storage-deploy` 文件夹  
3. 获得Bag ID

### 方式3: 等待其他TON Storage服务
TON生态中可能还会出现其他易用的TON Storage服务。

## 🌐 临时方案：使用GitHub Pages + TON DNS重定向

如果TON Storage暂时难以部署，您可以先：
1. 使用GitHub Pages（已就绪）: https://anglee0323.github.io/greatestofalltime.ton/
2. 在TON DNS中尝试将域名设置为钱包地址
3. 或寻找支持重定向到外部URL的TON代理服务

## 部署到GitHub Pages

### 步骤1: 创建GitHub仓库
1. 在GitHub上创建新仓库
2. 上传所有文件到仓库

### 步骤2: 启用GitHub Pages
1. 进入仓库 Settings → Pages
2. Source 选择 "GitHub Actions"
3. 保存设置

### 步骤3: 访问网站
- 自动部署完成后访问: `https://yourusername.github.io/greatestofalltime.ton`

## 连接TON域名 (可选)

如果您有 `greatestofalltime.ton` 域名：

1. 安装 [TON Chrome扩展](https://chrome.google.com/webstore/detail/ton-wallet/nphplpgoakhhjchkkhmiggakijnkhfnd)
2. 导入持有域名的钱包
3. 访问 [dns.ton.org](https://dns.ton.org)
4. 编辑您的域名，在"Site"字段填入GitHub Pages URL
5. 保存并确认交易

## 修改内容

编辑 `index.html` 文件中的这一行：
```html
<h1 class="main-message">我是最强的区块链天才！！！！！</h1>
```