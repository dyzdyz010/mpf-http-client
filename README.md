# MPF HTTP Client

Qt Modular Plugin Framework - HTTP Client Library

## 概述

提供简单易用的 HTTP 客户端 API，支持 GET/POST/PUT/DELETE 等方法。

## 依赖

- Qt 6.5+ (Core, Network)
- mpf-sdk

## 安装

### 从源码构建

```bash
export QT_DIR=/path/to/qt6
export MPF_SDK=/path/to/mpf-sdk

cmake -B build -G Ninja \
    -DCMAKE_PREFIX_PATH="$QT_DIR;$MPF_SDK" \
    -DCMAKE_INSTALL_PREFIX="$MPF_SDK"
cmake --build build
cmake --install build
```

### 从 Releases 下载

```bash
curl -LO https://github.com/dyzdyz010/mpf-http-client/releases/latest/download/mpf-http-client-linux-x64.tar.gz
tar -xzf mpf-http-client-linux-x64.tar.gz -C ~/mpf-sdk
```

## 使用

```cpp
#include <mpf/http/http_client.h>

auto client = std::make_unique<HttpClient>(this);
client->get(QUrl("https://api.example.com/data"));
connect(client.get(), &HttpClient::finished, this, [](const QByteArray& data) {
    qDebug() << data;
});
```

## 许可证

MIT License
