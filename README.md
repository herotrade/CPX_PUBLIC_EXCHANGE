# CPX Exchange - Open Source Cryptocurrency Exchange Platform
## 开源加密货币交易所 | 数字资产交易平台 | Bitcoin Trading System

![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)
![PHP](https://img.shields.io/badge/PHP-8.2+-777BB4?logo=php)
![Go](https://img.shields.io/badge/Go-1.21+-00ADD8?logo=go)
![Flutter](https://img.shields.io/badge/Flutter-3.7+-02569B?logo=flutter)
![GitHub stars](https://img.shields.io/github/stars/herotrade/CPX_PUBLIC_EXCHANGE?style=social)
![GitHub forks](https://img.shields.io/github/forks/herotrade/CPX_PUBLIC_EXCHANGE?style=social)

[English](README_EN.md) | [日本語](README_JP.md) | [한국어](README_KR.md) | 简体中文

## 📖 项目简介

**CPX Exchange** 是一个**完整开源的加密货币交易所解决方案**，采用**微服务架构**设计，提供**高性能、高可用**的数字资产交易平台。本项目适用于构建 **Bitcoin (BTC)**、**Ethereum (ETH)**、**USDT** 等加密货币的现货交易和合约交易平台。

### 关键词
`cryptocurrency exchange` `crypto trading platform` `bitcoin exchange` `open source exchange` `trading engine` `匹配引擎` `撮合系统` `数字货币交易所` `区块链` `DeFi` `fintech` `microservices`

### 核心特性
- ✅ **完整的交易所系统**：包含移动端、Web端、后台管理、交易引擎
- ✅ **高性能撮合引擎**：Go 语言开发，支持每秒百万级订单处理
- ✅ **多端支持**：Flutter 跨平台（iOS/Android）+ Web 管理后台
- ✅ **企业级安全**：2FA、KYC、WebAuthn、生物识别、风控系统
- ✅ **微服务架构**：Go + PHP + Flutter，可独立部署扩展
- ✅ **开箱即用**：完整源码，详细文档，快速部署

## 🌟 为什么选择 CPX Exchange？

相比其他开源交易所方案，CPX Exchange 提供：
- **生产级代码质量**：已经过商业项目验证
- **现代技术栈**：Go 1.21 + PHP 8.2 + Flutter 3.7
- **完整功能**：不仅是交易引擎，包含完整的业务系统
- **活跃维护**：持续更新和社区支持
- **中文文档**：适合中文开发者

## 🔗 快速链接

- 📱 **官方演示**: [https://www.bbbtrade.net](https://www.bbbtrade.net)
- 📧 **联系我们**: @chenmaq
- 📖 **完整文档**: [查看文档](./docs)
- 💬 **技术支持**: [提交 Issue](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE/issues)
- ⭐ **Star 本项目**: 如果觉得有用，请给我们一个 Star！

## 🏗️ 系统架构

本项目由三个主要子系统组成：

### 1️⃣ CPX-EXCHANGE-MOBILE (移动端应用)
基于 Flutter 构建的跨平台移动应用，支持 iOS 和 Android 系统。

**核心技术栈：**
- **框架**: Flutter 3.7.2+ / Dart
- **状态管理**: Provider
- **网络请求**: Dio, HTTP, WebSocket
- **本地存储**: Hive, Shared Preferences
- **身份认证**:
  - Google Sign In
  - Apple Sign In
  - 生物识别 (Local Auth)
  - WebAuthn
  - Google 2FA
- **UI组件库**:
  - Syncfusion Charts & Gauges (数据可视化)
  - FL Chart (雷达图等高级图表)
  - Lottie & Flutter Animate (动画效果)
  - Shimmer (骨架屏加载)
- **实名认证**:
  - Microblink BlinkID (证件扫描)
  - Google ML Kit (文本识别、人脸检测)
  - Mobile Scanner (二维码扫描)
- **推送通知**: Firebase Cloud Messaging
- **国际化**: Flutter Localizations, Intl
- **加密安全**: PointyCastle, Crypto
- **其他特性**:
  - 极验验证 (GT4)
  - WebView 集成
  - 图片/视频处理
  - 分享功能
  - 游戏引擎 (Flame)

**主要功能：**
- 实时行情查看与K线图表
- 现货/合约交易
- 资产管理与钱包功能
- 充值提现
- KYC实名认证
- 安全设置（2FA、生物识别）
- 多语言支持

---

### 2️⃣ CPX_EXCHANGE (后台管理系统)
基于 PHP Hyperf 框架构建的高性能后端服务。

**核心技术栈：**
- **框架**: Hyperf 3.1 (基于 Swoole 协程)
- **PHP 版本**: PHP 8.2+
- **Web 服务器**: Swoole 5.0+
- **数据库**:
  - MySQL (主数据库)
  - PostgreSQL (扩展支持)
  - Redis (缓存与队列)
  - Elasticsearch (搜索引擎)
- **核心库**:
  - MineAdmin (后台管理框架)
  - Firebase JWT (令牌认证)
  - WebAuthn (无密码认证)
  - Google2FA (双因素认证)
  - Firebase PHP (推送服务)
- **云服务集成**:
  - 阿里云 OSS (对象存储)
  - 阿里云短信服务
  - 阿里云实人认证
  - 阿里云邮件推送
- **其他特性**:
  - 异步队列 (Async Queue)
  - 定时任务 (Crontab)
  - WebSocket 服务器
  - Guzzle HTTP 客户端
  - 消息序列化 (MessagePack)

**主要功能：**
- 用户管理与权限控制
- 交易管理与风控系统
- 资产管理
- KYC审核
- 财务管理
- 系统配置与监控
- API接口服务

---

### 3️⃣ CPX_GO_SERVER (高性能交易引擎)
基于 Go 语言构建的微服务集群，负责核心交易撮合与实时数据推送。

**核心技术栈：**
- **语言**: Go 1.21+
- **Web 框架**: Fiber v2 (高性能 HTTP 框架)
- **数据库**:
  - MySQL (GORM)
  - Redis (go-redis v9)
- **WebSocket**:
  - gobwas/ws (高性能 WebSocket)
  - nhooyr.io/websocket
- **序列化**:
  - MessagePack (vmihailenco)
  - JSON Iterator
- **认证**: JWT (golang-jwt/jwt)
- **工具库**:
  - UUID (google/uuid)
  - Decimal (精确数值计算)

**微服务架构：**

```
CPX_GO_SERVER/
├── services/
│   ├── api-v2/          # API 网关服务
│   ├── match-engine/    # 撮合引擎
│   ├── market-maker/    # 做市商服务
│   ├── ws-gateway/      # WebSocket 网关
│   └── common/          # 公共库
```

**主要功能：**
- **match-engine**: 订单撮合引擎，处理买卖盘匹配
- **ws-gateway**: WebSocket服务，推送实时行情、订单、成交数据
- **api-v2**: RESTful API服务，提供交易接口
- **market-maker**: 做市商服务，提供流动性
- **market-data**: K线数据同步与分发

---

## 🔧 技术特点

### 高性能架构
- **Go 撮合引擎**: 微秒级订单撮合，支持高并发交易
- **Swoole 协程**: PHP后端采用协程架构，大幅提升并发处理能力
- **Redis 缓存**: 多级缓存策略，减少数据库压力
- **WebSocket 实时推送**: 毫秒级行情数据推送

### 安全性
- **多重身份验证**: 支持密码、2FA、生物识别、WebAuthn
- **JWT 令牌**: 无状态认证机制
- **KYC实名认证**: 集成证件扫描与活体检测
- **加密通信**: 全链路 HTTPS/WSS 加密
- **风控系统**: 实时风险监控与预警

### 可扩展性
- **微服务架构**: 各服务独立部署，易于水平扩展
- **消息队列**: 异步处理，削峰填谷
- **云原生**: 支持 Docker/Kubernetes 容器化部署
- **多数据库支持**: MySQL、PostgreSQL、Redis、Elasticsearch

### 用户体验
- **跨平台**: iOS、Android、Web 全平台覆盖
- **国际化**: 多语言支持
- **实时行情**: WebSocket 推送，无需刷新
- **富图表**: 专业级K线图与技术指标
- **流畅动画**: Lottie 与原生动画结合

---

## 📦 快速开始

### 前置要求

**移动端开发环境：**
- Flutter SDK 3.7.2+
- Dart SDK
- iOS: Xcode 14+, CocoaPods
- Android: Android Studio, JDK 11+

**后端开发环境：**
- PHP 8.2+
- Composer
- Swoole 5.0+
- MySQL 8.0+
- Redis 6.0+

**Go 服务开发环境：**
- Go 1.21+
- MySQL 8.0+
- Redis 6.0+

### 安装与运行

#### 1. 移动端应用

```bash
# 进入移动端项目目录
cd CPX-EXCHANGE-MOBILE

# 安装依赖
flutter pub get

# 运行代码生成
flutter pub run build_runner build

# 运行应用 (iOS)
flutter run -d ios

# 运行应用 (Android)
flutter run -d android

# 构建生产版本
flutter build apk --release  # Android
flutter build ios --release  # iOS
```

#### 2. 后台管理系统

```bash
# 进入后端项目目录
cd CPX_EXCHANGE

# 安装依赖
composer install

# 复制环境配置
cp .env.example .env

# 配置数据库连接（编辑 .env 文件）

# 启动服务
composer start

# 开发模式（热重载）
composer dev
```

#### 3. Go 交易引擎

```bash
# 进入 Go 服务目录
cd CPX_GO_SERVER/services

# 启动撮合引擎
cd match-engine
go mod download
go run cmd/match-engine/main.go

# 启动 WebSocket 网关
cd ../ws-gateway
go mod download
go run cmd/ws-gateway/main.go

# 启动 API 服务
cd ../api-v2
go mod download
go run cmd/api/main.go
```

---

## 🔐 环境配置

### 移动端配置

编辑 `CPX-EXCHANGE-MOBILE/.env` 或配置文件：

```env
API_BASE_URL=https://api.yourdomain.com
WS_URL=wss://ws.yourdomain.com
FIREBASE_PROJECT_ID=your-project-id
```

### 后端配置

编辑 `CPX_EXCHANGE/.env`：

```env
APP_NAME=CPX-Exchange
APP_ENV=production
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=cpx_exchange
DB_USERNAME=root
DB_PASSWORD=

REDIS_HOST=127.0.0.1
REDIS_PORT=6379
```

### Go 服务配置

编辑 `CPX_GO_SERVER/.env`：

```env
DB_HOST=localhost
DB_PORT=3306
DB_NAME=cpx_trading
REDIS_ADDR=localhost:6379
WS_PORT=8080
```

---

## 📊 系统架构图

```
┌─────────────────┐
│  Mobile App     │
│  (Flutter)      │
└────────┬────────┘
         │
         ├─────────────────┐
         │                 │
         ▼                 ▼
┌─────────────────┐  ┌──────────────────┐
│  PHP Backend    │  │  Go Services     │
│  (Hyperf)       │  │  ┌────────────┐  │
│  ┌───────────┐  │  │  │ Match Eng. │  │
│  │ Admin API │  │  │  │ WS Gateway │  │
│  │ User Mgmt │  │  │  │ API v2     │  │
│  │ KYC       │  │  │  │ Market MM  │  │
│  └───────────┘  │  │  └────────────┘  │
└────────┬────────┘  └────────┬─────────┘
         │                    │
         └──────┬─────────────┘
                ▼
        ┌───────────────┐
        │   Database    │
        │  MySQL/Redis  │
        └───────────────┘
```

---

## 🛠️ 技术栈总览

| 层级 | 技术选型 |
|------|----------|
| **移动端** | Flutter, Dart, Provider, Hive, Firebase |
| **后端服务** | PHP 8.2, Hyperf 3.1, Swoole 5.0 |
| **交易引擎** | Go 1.21, Fiber, GORM, go-redis |
| **数据库** | MySQL 8.0, PostgreSQL, Redis, Elasticsearch |
| **通信协议** | HTTP/HTTPS, WebSocket, MessagePack |
| **身份认证** | JWT, OAuth 2.0, WebAuthn, 2FA |
| **云服务** | 阿里云 OSS/SMS/Email, Firebase |
| **容器化** | Docker, Docker Compose |

---

## 📄 开源协议

本项目采用 [Apache License 2.0](LICENSE) 开源协议。

---

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建您的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交您的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启一个 Pull Request

---

## 📧 联系方式

- 官网: https://www.bbbtrade.net
- 邮箱: support@bbbtrade.net

---

## 🌐 社区与支持

### 加入我们的社区
- **GitHub**: [Star 和 Fork 本项目](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE)
- **Discussions**: [参与讨论](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE/discussions)
- **Issues**: [报告问题和建议](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE/issues)

### 商业支持
如需定制开发、技术咨询、私有化部署等商业服务，请联系：
- Email: support@bbbtrade.net
- Website: https://www.bbbtrade.net

---

## 🏆 成功案例

基于 CPX Exchange 构建的交易所已服务：
- 现货交易平台
- 合约交易系统
- NFT 交易市场
- DeFi 协议

---

## 📊 项目统计

- **代码行数**: 100,000+
- **支持语言**: 10+ (国际化)
- **支持币种**: 100+
- **性能**: 1,000,000+ TPS (撮合引擎)

---

## 🔍 相关关键词

**中文**: 加密货币交易所开发, 数字货币交易平台源码, 比特币交易系统, 以太坊交易所, 区块链交易平台, 撮合引擎, 币币交易, 合约交易系统, 加密资产管理, Web3 交易所

**English**: cryptocurrency exchange development, bitcoin trading platform, ethereum exchange, crypto trading system, blockchain exchange, order matching engine, spot trading, futures trading, crypto asset management, open source exchange, white label exchange

**日本語**: 暗号通貨取引所, ビットコイン取引プラットフォーム, 仮想通貨交換所

**한국어**: 암호화폐 거래소, 비트코인 거래 플랫폼, 디지털 자산 거래

---

## 🔗 相关项目

如果你对加密货币交易所开发感兴趣，可能还会喜欢：
- [awesome-crypto](https://github.com/topics/cryptocurrency)
- [trading-systems](https://github.com/topics/trading)
- [blockchain](https://github.com/topics/blockchain)

---

## 📖 延伸阅读

- [如何构建高性能加密货币交易所](https://www.bbbtrade.net/blog/building-crypto-exchange)
- [撮合引擎算法详解](https://www.bbbtrade.net/blog/matching-engine)
- [交易所安全最佳实践](https://www.bbbtrade.net/blog/exchange-security)

---

## ⚠️ 免责声明

本项目仅供学习和研究使用。在使用本系统进行实际交易前，请确保遵守所在国家/地区的法律法规，并获得必要的金融许可证。开发者不对使用本系统造成的任何损失负责。

**重要提示**：
- ⚖️ 加密货币交易在某些国家/地区可能受到监管限制
- 🔐 请确保实施充分的安全措施
- 📋 请咨询法律顾问确保合规性
- 💼 商业使用前请获取必要的金融许可证

---

## 📜 开源许可

本项目采用 Apache License 2.0 开源协议，你可以自由地：
- ✅ 商业使用
- ✅ 修改代码
- ✅ 分发
- ✅ 私有使用

但需要：
- 📝 保留版权声明
- 📝 声明修改内容
- 📝 包含许可证副本

---

## 🌟 Star History

如果这个项目对你有帮助，请给我们一个 Star！

[![Star History Chart](https://api.star-history.com/svg?repos=herotrade/CPX_PUBLIC_EXCHANGE&type=Date)](https://star-history.com/#herotrade/CPX_PUBLIC_EXCHANGE&Date)

---

**© 2024 CPX Exchange. All rights reserved.**

Made with ❤️ by the CPX Team | [GitHub](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE) | [Website](https://www.bbbtrade.net)
