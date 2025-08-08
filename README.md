# greatestofalltime.ton

一个极简个人网站，展示"我是最强的区块链天才！！！！！"

## 🚀 推荐：部署到TON Storage（完全去中心化，免费）

### 使用TON Byte部署
1. 访问 [tonbyte.com](https://tonbyte.com)
2. 创建账户并上传项目文件（主要是index.html和favicon.ico）
3. 获得Bag ID
4. 在TON DNS中将Bag ID填入"TON Storage"字段
5. 您的网站将通过TON网络完全去中心化运行！

### 手动TON Storage部署
1. 创建包含index.html的文件夹
2. 使用TON Storage工具创建bag
3. 上传到TON网络获得Bag ID
4. 在dns.ton.org中设置Bag ID

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