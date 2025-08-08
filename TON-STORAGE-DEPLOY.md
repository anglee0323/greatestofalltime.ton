# 🚀 TON Storage 部署指南

## 选定提供商信息

**推荐提供商**: 德国服务器
- **公钥**: bc0115e...42b3a857 (已复制)
- **位置**: 德国 (Germany)  
- **价格**: 仅需 **0.50 TON**
- **稳定性**: 100%稳定
- **运行时间**: 99.98%
- **评级**: 31.33

## 📋 部署步骤

### 步骤1: 准备TON Storage工具

```bash
# 下载storage-daemon (Linux)
wget https://github.com/ton-blockchain/ton/releases/latest/download/storage-daemon-linux-x86_64
chmod +x storage-daemon-linux-x86_64

# 对于macOS用户
wget https://github.com/ton-blockchain/ton/releases/latest/download/storage-daemon-darwin-x86_64
chmod +x storage-daemon-darwin-x86_64

# 对于Windows用户
# 下载 storage-daemon-windows-x86_64.exe
```

### 步骤2: 启动Storage Daemon

```bash
# 创建数据库目录并启动daemon
./storage-daemon-linux-x86_64 -C storage-db -I 127.0.0.1:5555

# daemon会在后台运行，监听5555端口
```

### 步骤3: 使用CLI创建Bag

```bash
# 连接到daemon
storage-daemon-cli -I 127.0.0.1:5555 -k storage-db/cli-keys/client -p storage-db/cli-keys/server.pub

# 在CLI中执行以下命令：
> create ton-storage-deploy/

# 这会创建一个bag并返回Bag ID，类似于：
# Bag ID: bag://abc123def456...
```

### 步骤4: 与提供商创建存储合约

```bash
# 在CLI中继续执行：
> new-contract-message <BagID> storage-contract.boc --query-id 0 --provider bc0115e42b3a857...

# 这会生成一个.boc文件，需要发送到TON网络
```

### 步骤5: 发送存储合约到TON网络

```bash
# 使用TON CLI或钱包发送合约
# 需要支付 0.50 TON 给提供商

# 合约成功后，您的文件将被分布到TON Storage网络
```

### 步骤6: 设置TON DNS

1. 访问 [dns.ton.org](https://dns.ton.org)
2. 打开您的 `greatestofalltime.ton` 域名
3. 点击 "Edit" 
4. 在 **"TON Storage"** 字段（不是"TON Site"字段！）填入您的 Bag ID
5. 保存交易

## ✅ 完成！

您的网站现在将通过完全去中心化的TON Storage网络运行！

访问 `greatestofalltime.ton` 将直接从TON网络加载您的"我是最强的区块链天才！！！！！"网站。

## 🔧 故障排除

- **Daemon启动失败**: 检查端口5555是否被占用
- **CLI连接失败**: 确认daemon正在运行且密钥文件存在
- **合约创建失败**: 确认您有足够的TON余额支付gas费用
- **DNS设置无效**: 确保填入的是TON Storage字段，不是TON Site字段

## 💰 费用说明

- **存储费用**: 0.50 TON (一次性支付给提供商)
- **Gas费用**: ~0.1 TON (网络交易费用)
- **总计**: 约 0.6 TON

比传统云服务器便宜多了，而且完全去中心化！