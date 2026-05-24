# 🏠 SmartHome

> 基于 Qt + ESP8266 的嵌入式智能家居控制系统

<p align="center">
  <img src="https://img.shields.io/badge/Framework-Qt5-41CD52?style=for-the-badge&logo=qt&logoColor=white" />
  <img src="https://img.shields.io/badge/WiFi-ESP8266-E7352C?style=for-the-badge&logo=espressif&logoColor=white" />
  <img src="https://img.shields.io/badge/Language-C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" />
  <img src="https://img.shields.io/badge/API-RESTful-FF6C37?style=for-the-badge" />
</p>

---

## 📖 简介

一套智能家居控制系统，由 **Qt5 上位机** 通过 WiFi (ESP8266) 与下位机通信，实现对家居设备的远程监控与控制。

---

## 🏗️ 系统架构

```
┌─────────────────────┐         WiFi / Serial          ┌──────────────┐
│   Qt5 上位机         │ ◄══════════════════════════► │  ESP8266      │
│                      │                               │  (TCP Server) │
│  · 开关控制面板       │                               └──────┬───────┘
│  · 状态实时显示       │                                      │
│  · RESTful API       │                               ┌──────▼───────┐
│  · QSS 美化界面       │                               │  LED 设备     │
└─────────────────────┘                               └──────────────┘
```

---

## 📂 项目结构

| 目录 | 说明 |
|:---|:---|
| `01_smarthome/` | Qt5 主应用程序（UI 界面、样式表、图标资源） |
| `esp8266/` | ESP8266 WiFi 模块通信驱动（AT 指令集） |
| `led/` | LED 灯控模块（开关控制、状态反馈） |
| `webapi/` | RESTful API 接口（远程调用、数据交互） |

---

## ✨ 核心功能

- 🎛️ **设备控制面板** — Qt 自定义开关按钮，一键控制家居设备
- 📶 **WiFi 无线通信** — ESP8266 实现上下位机数据传输
- 💡 **LED 智能控制** — 远程开关、状态查询
- 🌐 **RESTful API** — 标准化接口，支持第三方接入
- 🎨 **QSS 美化** — 自定义 UI 样式，现代化界面设计

---

## 🚀 快速开始

### 环境要求

| 工具 | 版本 |
|:---|:---|
| Qt Creator | 5.x |
| 编译器 | MinGW / MSVC |
| ESP8266 | AT 固件 v1.6+ |
| 硬件 | USB-TTL 串口模块 |

### 编译运行

1. 用 Qt Creator 打开 `01_smarthome.pro`
2. 选择构建套件 (MinGW 32-bit)
3. 编译运行 (`Ctrl + R`)

### 硬件连接

```
ESP8266 TX  ↔  USB-TTL RX
ESP8266 RX  ↔  USB-TTL TX
ESP8266 VCC ↔  3.3V
ESP8266 GND ↔  GND
LED 控制引脚 ↔  对应 GPIO
```

---

## 🔧 模块说明

### ESP8266 驱动 (`esp8266/`)

封装 AT 指令集，支持 TCP Server 模式，实现 WiFi 无线数据传输。

### LED 控制 (`led/`)

提供开关控制、状态读取接口，支持多路 LED 独立管理。

### WebAPI (`webapi/`)

RESTful 风格接口设计，为移动端或 Web 端接入预留标准 API。

---

<p align="center">
  <sub>Embedded · IoT · Smart Home</sub>
</p>
