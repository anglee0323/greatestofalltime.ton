# greatestofalltime.ton

一个极简个人网站，展示"我是最强的区块链天才！！！！！"

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