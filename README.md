# 🧠 AI Lab SND

> **Smart Nutrition Detector** — A privacy-first, cross-platform AI nutrition analysis system that runs on **ESP32-S3 edge devices**, **desktop apps**, and **web dashboards**.

![License](https://img.shields.io/badge/license-MIT-green.svg)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20ESP32-blue.svg)
![Python](https://img.shields.io/badge/python-3.10%2B-yellow.svg)
![Node](https://img.shields.io/badge/node-18%2B-brightgreen.svg)
![Status](https://img.shields.io/badge/status-active%20development-orange.svg)

---

## 📖 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Installation](#-installation)
- [Usage](#-usage)
- [Hardware Setup](#-hardware-setup)
- [API Documentation](#-api-documentation)
- [Development](#-development)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)
- [Support](#-support)

---

## 🎯 About

**AI Lab SND** is a complete end-to-end **Edge AI nutrition detection platform**. It combines:

- 🔬 **Computer vision** to recognize food items from camera input
- 🧮 **Nutrition analysis** (calories, macros, allergens, glycemic index)
- 📊 **Health tracking** with personalized recommendations
- 🔒 **Privacy-first** — all AI inference runs **locally on-device**
- 🌐 **Multi-platform** — ESP32 edge device, desktop app, web dashboard

Perfect for:
- 🏋️ Fitness enthusiasts tracking macros
- 🏥 Patients managing dietary restrictions (diabetes, allergies, etc.)
- 👨‍🍳 Home cooks learning about ingredients
- 🧪 Researchers studying food recognition AI

---

## ✨ Features

### 🎥 Vision & Recognition
- Real-time food detection via camera (ESP32-S3-CAM or webcam)
- 1000+ food class recognition
- Portion size estimation using reference objects
- Multi-item plate detection

### 📊 Nutrition Analysis
- Automatic calorie counting
- Full macro breakdown (protein, carbs, fat, fiber)
- Allergen detection (gluten, lactose, nuts, etc.)
- Glycemic index estimation
- Vitamin & mineral tracking

### 🏃 Health Features
- Daily/weekly/monthly intake dashboards
- Personalized goals (weight loss, muscle gain, maintenance)
- Hydration tracking
- Meal history with photos
- Export reports (PDF, CSV, JSON)

### 🔐 Privacy & Security
- **100% on-device inference** — no data leaves your device by default
- Optional encrypted cloud sync
- Local SQLite database
- End-to-end encryption for multi-device sync

### 🌍 Multi-Platform
- 🖥️ **Desktop App** (Windows, macOS, Linux) — Electron
- 📱 **Mobile-ready API** — ready for React Native wrapper
- 🌐 **Web Dashboard** — Next.js + Tailwind
- 🔌 **ESP32-S3 Edge Device** — standalone portable scanner
- ☁️ **Optional cloud backend** — self-hostable

---

## 🏗 Architecture

┌─────────────────────────────────────────────────────────────┐
│ AI LAB SND SYSTEM │
└─────────────────────────────────────────────────────────────┘

┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│ ESP32-S3 │ │ Desktop │ │ Web │
│ Edge Cam │ │ (Electron) │ │ (Next.js) │
└──────┬───────┘ └──────┬───────┘ └──────┬───────┘
│ │ │
│ BLE / WiFi │ HTTP / IPC │ HTTPS
└─────────┬─────────┴─────────┬─────────┘
│ │
┌─────────▼───────────────────▼─────────┐
│ Local AI Inference Engine │
│ (TensorFlow Lite + ONNX Runtime) │
└─────────┬─────────────────────────────┘
│
┌─────────▼─────────┐
│ SQLite Database │
│ (Encrypted) │
└───────────────────┘

markdown

---

## 🛠 Tech Stack

### Frontend
- **Desktop**: Electron, React, TypeScript, TailwindCSS
- **Web**: Next.js 14, React, TypeScript, TailwindCSS, shadcn/ui
- **State**: Zustand, React Query

### Backend
- **API**: FastAPI (Python 3.10+)
- **Database**: SQLite (local) + PostgreSQL (optional cloud)
- **Auth**: JWT + bcrypt
- **Realtime**: WebSockets

### AI / ML
- **Vision Model**: YOLOv8n (food detection) + MobileNetV3 (classification)
- **Inference**: TensorFlow Lite, ONNX Runtime
- **Training**: PyTorch, Ultralytics
- **Data**: Food-101, Nutrition5k, custom dataset

### Hardware (Edge)
- **MCU**: ESP32-S3-WROOM
- **Camera**: OV2640 / OV5640
- **Display**: 1.9" IPS TFT (170x320)
- **Firmware**: ESP-IDF (C/C++) + Arduino framework

### DevOps
- **Build**: Vite, electron-builder
- **CI/CD**: GitHub Actions
- **Testing**: Pytest, Jest, Playwright
- **Docs**: MkDocs Material

---

## 📁 Project Structure

ai-lab-snd/
├── apps/
│ ├── desktop/ # Electron desktop app
│ ├── web/ # Next.js web dashboard
│ └── mobile/ # (future) React Native app
├── services/
│ ├── api/ # FastAPI backend
│ ├── inference/ # AI inference service
│ └── sync/ # Cloud sync service
├── firmware/
│ └── esp32-snd/ # ESP32-S3 firmware
├── ai/
│ ├── models/ # Trained models (.tflite, .onnx)
│ ├── training/ # Training scripts
│ └── datasets/ # Dataset tools
├── packages/
│ ├── shared/ # Shared TypeScript types
│ ├── ui/ # Shared UI components
│ └── utils/ # Shared utilities
├── docs/ # Documentation
├── scripts/ # Build & deploy scripts
└── tests/ # Integration tests

mipsasm

---

## 🚀 Getting Started

### Prerequisites

Before you begin, make sure you have installed:

- **Node.js** 18+ ([download](https://nodejs.org/))
- **Python** 3.10+ ([download](https://www.python.org/))
- **Git** ([download](https://git-scm.com/))
- **PlatformIO** (for ESP32 firmware, optional)

### Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/ai-lab-snd.git
cd ai-lab-snd

# 2. Install dependencies
npm install
pip install -r requirements.txt

# 3. Run the desktop app
npm run dev:desktop

# 4. Run the web app (separate terminal)
npm run dev:web

# 5. Run the API (separate terminal)
npm run dev:api


📦 Installation
Desktop App
Download pre-built installers from the Releases page:

Windows: AI-Lab-SND-Setup-x.x.x.exe
macOS: AI-Lab-SND-x.x.x.dmg
Linux: AI-Lab-SND-x.x.x.AppImage
Web Dashboard
Visit the hosted version: https://your-domain.com

Or self-host it (see Deployment Guide).

💡 Usage
1. Scan Food with Camera
Launch the desktop app → Click "Scan" → Point camera at food → Instant nutrition breakdown.

2. Add Meal Manually
Click "Add Meal" → Search food database → Set portion → Save.

3. View Dashboard
Open the Dashboard tab to see:

Today's calorie intake
Macro distribution
Weekly trends
Goal progress
4. Connect ESP32 Scanner
Settings → Devices → Pair ESP32 → Point device camera at food → Results appear on both the device screen and desktop app.

🔌 Hardware Setup
For the full ESP32-S3 edge scanner build, see:

📘 Hardware Build Guide

Required components:

ESP32-S3-WROOM dev board
OV2640 camera module
1.9" IPS display
3.7V LiPo battery (1200mAh+)
Enclosure (3D printable, STL files included)
📚 API Documentation
Full REST API documentation available at /docs when running the API locally:

http://localhost:8000/docs

Interactive Swagger UI with all endpoints, request/response schemas, and example payloads.

👨‍💻 Development
Running Tests
bash
npm test              # All tests
npm run test:unit     # Unit tests only
npm run test:e2e      # End-to-end tests
pytest                # Python tests

Linting & Formatting
bash
npm run lint          # ESLint + Prettier
npm run format        # Auto-fix formatting
ruff check .          # Python linting

Building for Production
bash
npm run build:desktop # Builds desktop installers
npm run build:web     # Builds web app
npm run build:all     # Builds everything

🗺 Roadmap
 Project scaffolding
 Desktop app skeleton
 Web dashboard skeleton
 Core nutrition database
 Food recognition model v1
 ESP32 firmware v1
 Cloud sync service
 Mobile app (React Native)
 Barcode scanning
 Recipe suggestions
 Social features (share meals)
 Smartwatch integration
See the full Roadmap.

🤝 Contributing
Contributions are welcome! Please read CONTRIBUTING.md for guidelines.

Fork the repo
Create your feature branch (git checkout -b feature/amazing-feature)
Commit your changes (git commit -m 'Add amazing feature')
Push to the branch (git push origin feature/amazing-feature)
Open a Pull Request
📄 License
This project is licensed under the MIT License — see the LICENSE file for details.

💬 Support
📧 Email: support@ai-lab-snd.local
🐛 Bug reports: GitHub Issues
💡 Feature requests: GitHub Discussions
📖 Docs: Full Documentation
🙏 Acknowledgments
Food-101 dataset
Nutrition5k
Ultralytics YOLOv8
TensorFlow Lite
The open-source community ❤️
<p align="center">

<strong>Made with ❤️ by the AI Lab SND Team</strong><br>

<sub>Edge AI for a healthier world 🌍</sub>

</p>

```

