# CPX Exchange - Open Source Cryptocurrency Exchange Platform

![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)
![PHP](https://img.shields.io/badge/PHP-8.2+-777BB4?logo=php)
![Go](https://img.shields.io/badge/Go-1.21+-00ADD8?logo=go)
![Flutter](https://img.shields.io/badge/Flutter-3.7+-02569B?logo=flutter)
![GitHub stars](https://img.shields.io/github/stars/herotrade/CPX_PUBLIC_EXCHANGE?style=social)

English | [简体中文](README.md) | [日本語](README_JP.md) | [한국어](README_KR.md)

## 📖 Overview

**CPX Exchange** is a **complete open-source cryptocurrency exchange solution** built with **microservices architecture**, providing a **high-performance, high-availability** digital asset trading platform. This project is suitable for building spot and futures trading platforms for cryptocurrencies like **Bitcoin (BTC)**, **Ethereum (ETH)**, **USDT**, and more.

### Keywords
`cryptocurrency exchange` `crypto trading platform` `bitcoin exchange` `ethereum trading` `open source exchange` `trading engine` `matching engine` `order book` `blockchain` `DeFi` `fintech` `microservices` `white label exchange`

### Key Features
- ✅ **Complete Exchange System**: Mobile app, Web dashboard, Admin panel, Trading engine
- ✅ **High-Performance Matching Engine**: Go-based, supports 1M+ orders per second
- ✅ **Multi-Platform Support**: Flutter cross-platform (iOS/Android) + Web admin
- ✅ **Enterprise Security**: 2FA, KYC, WebAuthn, Biometric authentication, Risk control
- ✅ **Microservices Architecture**: Go + PHP + Flutter, independently deployable
- ✅ **Production-Ready**: Complete source code, detailed documentation, fast deployment

## 🌟 Why Choose CPX Exchange?

Compared to other open-source exchange solutions, CPX Exchange offers:
- **Production-Grade Code**: Battle-tested in commercial projects
- **Modern Tech Stack**: Go 1.21 + PHP 8.2 + Flutter 3.7
- **Complete Features**: Not just trading engine, but full business system
- **Active Maintenance**: Continuous updates and community support
- **Comprehensive Documentation**: Easy to understand and deploy

## 🚀 Quick Links

- 📱 **Live Demo**: [https://www.bbbtrade.net](https://www.bbbtrade.net)
- 📧 **Contact**: @chenmaq
- 📖 **Documentation**: [View Docs](./docs)
- 💬 **Support**: [Submit Issue](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE/issues)
- ⭐ **Star Us**: If you find this useful, please give us a star!

---

## 🏗️ System Architecture

The project consists of three main subsystems:

### 1️⃣ CPX-EXCHANGE-MOBILE (Mobile Application)
Flutter-based cross-platform mobile app for iOS and Android.

**Tech Stack:**
- **Framework**: Flutter 3.7.2+ / Dart
- **State Management**: Provider
- **Networking**: Dio, HTTP, WebSocket
- **Authentication**: Google Sign In, Apple Sign In, Local Auth, WebAuthn, 2FA
- **Charts**: Syncfusion Charts, FL Chart
- **KYC**: Microblink BlinkID, Google ML Kit
- **Push Notifications**: Firebase Cloud Messaging
- **Security**: PointyCastle, Crypto

**Features:**
- Real-time market data and K-line charts
- Spot & Futures trading
- Asset management and wallet
- Deposit & Withdrawal
- KYC verification
- Security settings (2FA, Biometric)
- Multi-language support

---

### 2️⃣ CPX_EXCHANGE (Backend Admin System)
High-performance backend service built with PHP Hyperf framework.

**Tech Stack:**
- **Framework**: Hyperf 3.1 (Swoole coroutines)
- **PHP Version**: PHP 8.2+
- **Web Server**: Swoole 5.0+
- **Databases**: MySQL, PostgreSQL, Redis, Elasticsearch
- **Core Libraries**: MineAdmin, Firebase JWT, WebAuthn, Google2FA
- **Cloud Services**: Alibaba Cloud OSS/SMS/Email, Firebase

**Features:**
- User management & permissions
- Trading management & risk control
- Asset management
- KYC approval
- Financial management
- System configuration & monitoring
- REST API services

---

### 3️⃣ CPX_GO_SERVER (High-Performance Trading Engine)
Microservices cluster built with Go for core trading matching and real-time data streaming.

**Tech Stack:**
- **Language**: Go 1.21+
- **Web Framework**: Fiber v2
- **Databases**: MySQL (GORM), Redis (go-redis v9)
- **WebSocket**: gobwas/ws, nhooyr.io/websocket
- **Serialization**: MessagePack, JSON Iterator
- **Authentication**: JWT

**Microservices:**
```
CPX_GO_SERVER/
├── services/
│   ├── api-v2/          # API Gateway
│   ├── match-engine/    # Order Matching Engine
│   ├── market-maker/    # Market Maker Service
│   ├── ws-gateway/      # WebSocket Gateway
│   └── common/          # Shared Libraries
```

**Features:**
- **match-engine**: Order matching with microsecond latency
- **ws-gateway**: Real-time market data streaming
- **api-v2**: RESTful trading APIs
- **market-maker**: Liquidity provision
- **market-data**: K-line data synchronization

---

## 🔧 Technical Highlights

### High Performance
- **Go Matching Engine**: Microsecond-level order matching
- **Swoole Coroutines**: High-concurrency PHP backend
- **Redis Caching**: Multi-level caching strategy
- **WebSocket Streaming**: Millisecond-level data push

### Security
- **Multi-Factor Authentication**: Password, 2FA, Biometric, WebAuthn
- **JWT Tokens**: Stateless authentication
- **KYC Verification**: ID scanning and liveness detection
- **Encrypted Communication**: Full HTTPS/WSS encryption
- **Risk Control**: Real-time monitoring and alerts

### Scalability
- **Microservices**: Independent deployment and horizontal scaling
- **Message Queues**: Asynchronous processing
- **Cloud Native**: Docker/Kubernetes support
- **Multi-Database**: MySQL, PostgreSQL, Redis, Elasticsearch

---

## 📦 Quick Start

### Prerequisites

**Mobile Development:**
- Flutter SDK 3.7.2+
- Dart SDK
- iOS: Xcode 14+, CocoaPods
- Android: Android Studio, JDK 11+

**Backend Development:**
- PHP 8.2+
- Composer
- Swoole 5.0+
- MySQL 8.0+
- Redis 6.0+

**Go Services:**
- Go 1.21+
- MySQL 8.0+
- Redis 6.0+

### Installation

#### 1. Mobile App

```bash
cd CPX-EXCHANGE-MOBILE
flutter pub get
flutter pub run build_runner build
flutter run
```

#### 2. Backend Admin

```bash
cd CPX_EXCHANGE
composer install
cp .env.example .env
# Configure database in .env
composer start
```

#### 3. Go Trading Engine

```bash
cd CPX_GO_SERVER/services/match-engine
go mod download
go run cmd/match-engine/main.go
```

---

## 🛠️ Tech Stack Overview

| Layer | Technologies |
|-------|--------------|
| **Mobile** | Flutter, Dart, Provider, Hive, Firebase |
| **Backend** | PHP 8.2, Hyperf 3.1, Swoole 5.0 |
| **Trading Engine** | Go 1.21, Fiber, GORM, go-redis |
| **Databases** | MySQL 8.0, PostgreSQL, Redis, Elasticsearch |
| **Protocols** | HTTP/HTTPS, WebSocket, MessagePack |
| **Authentication** | JWT, OAuth 2.0, WebAuthn, 2FA |
| **Cloud Services** | Alibaba Cloud, Firebase |
| **DevOps** | Docker, Docker Compose, Kubernetes |

---

## 🌐 Community & Support

### Join Our Community
- **GitHub**: [Star and Fork](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE)
- **Discussions**: [Join Discussion](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE/discussions)
- **Issues**: [Report Issues](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE/issues)

### Commercial Support
For custom development, technical consulting, and private deployment:
- Email: support@bbbtrade.net
- Website: https://www.bbbtrade.net

---

## 📊 Project Stats

- **Lines of Code**: 100,000+
- **Supported Languages**: 10+ (i18n)
- **Supported Coins**: 100+
- **Performance**: 1,000,000+ TPS (matching engine)

---

## 🔍 Related Keywords

**Trading**: spot trading, futures trading, margin trading, leverage trading, cryptocurrency derivatives, perpetual contracts, order book, limit order, market order, stop loss, take profit

**Technology**: matching engine, order matching algorithm, high frequency trading, low latency, real-time trading, trading bot, API trading, algorithmic trading

**Blockchain**: Bitcoin, Ethereum, BNB, Solana, Cardano, Polkadot, DeFi, Web3, smart contracts, blockchain development

**Exchange**: cryptocurrency exchange, crypto trading platform, digital asset exchange, bitcoin exchange, ethereum exchange, altcoin trading, token listing

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## ⚠️ Disclaimer

This project is for educational and research purposes only. Before using this system for actual trading, ensure compliance with your local laws and regulations and obtain necessary financial licenses. Developers are not responsible for any losses incurred.

**Important Notice:**
- ⚖️ Cryptocurrency trading may be regulated in certain jurisdictions
- 🔐 Ensure adequate security measures are implemented
- 📋 Consult legal counsel for compliance
- 💼 Obtain necessary licenses for commercial use

---

## 📜 License

Licensed under Apache License 2.0. You are free to:
- ✅ Commercial use
- ✅ Modify code
- ✅ Distribute
- ✅ Private use

With requirements:
- 📝 Include copyright notice
- 📝 State changes
- 📝 Include license copy

---

## 🌟 Star History

If this project helps you, please give us a star!

[![Star History Chart](https://api.star-history.com/svg?repos=herotrade/CPX_PUBLIC_EXCHANGE&type=Date)](https://star-history.com/#herotrade/CPX_PUBLIC_EXCHANGE&Date)

---

**© 2024 CPX Exchange. All rights reserved.**

Made with ❤️ by the CPX Team | [GitHub](https://github.com/herotrade/CPX_PUBLIC_EXCHANGE) | [Website](https://www.bbbtrade.net)
