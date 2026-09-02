# WebOS — Browser-Based Desktop Operating System

[![Live Demo](https://img.shields.io/badge/Live_Demo-web--os--beta--two.vercel.app-blue?style=flat-square&logo=vercel)](https://web-os-beta-two.vercel.app)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-6.x-646CFF?style=flat-square&logo=vite)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.x-38B2AC?style=flat-square&logo=tailwind-css)](https://tailwindcss.com/)
[![Zustand](https://img.shields.io/badge/State-Zustand-orange?style=flat-square)](https://github.com/pmndrs/zustand)
[![GSAP](https://img.shields.io/badge/Animations-GSAP-88CE02?style=flat-square&logo=greensock)](https://greensock.com/)
[![Node.js & Express](https://img.shields.io/badge/Backend-Express_5_%26_Socket.IO-black?style=flat-square&logo=express)](https://expressjs.com/)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=flat-square&logo=docker)](https://www.docker.com/)

An interactive, high-performance web desktop operating system environment engineered with React 19, Vite, Tailwind CSS, GSAP, and a real-time Express & Socket.IO backend. WebOS simulates a native multi-window desktop interface entirely in modern web browsers.

---

## 📌 Overview

Traditional web applications enforce rigid page-by-page navigations. **WebOS** reimagines the browser viewport as an interactive operating system desktop, providing non-blocking multitasking, a draggable multi-window manager, desktop widgets, a virtual command-line terminal emulator, and an integrated AI assistant powered by Google Gemini.

---

## ✨ Key Features

### 🖥️ Desktop & Window Management
- **Draggable & Resizable Windows:** Complete windowing system supporting dragging, resizing, minimizing, maximizing, and z-index focal stacking.
- **macOS-Style Dock:** Fluid icon shelf with magnification effects powered by GSAP animation timelines.
- **Top Navigation Bar:** Persistent system bar with active process indicators, live clock, control center, and volume sliders.

### 📦 Built-In Applications
- **AI Assistant ("Ask AI"):** Conversational interface integrated with Google Gemini API for natural-language inquiries.
- **Terminal Emulator:** Interactive shell supporting file system navigation (`cd`, `ls`, `cat`), system diagnostics, and environment inspect commands.
- **Code Studio:** In-browser code editing environment with syntax highlighting.
- **File Explorer / Finder:** Hierarchical navigation through a virtual filesystem.
- **Media & Document Viewers:** Embedded PDF viewer (`react-pdf`) and responsive image gallery.
- **Utilities Suite:** Interactive calculator, system calendar, notes pad, and weather monitor.

### ⚡ Real-Time Backend & Security
- **Socket.IO Telemetry & Messaging:** Bi-directional event communication for chat and WebRTC video call signaling.
- **Hardened API Surface:** Built with Express 5, Helmet, rate-limiting (`express-rate-limit`), MongoDB sanitization, XSS filtering, and Joi payload validation.
- **Automated Testing:** Test suites configured with Vitest for frontend components and Jest + Supertest for backend endpoints.

---

## 🛠️ Tech Stack

| Layer | Technologies |
| :--- | :--- |
| **Frontend Core** | React 19, JavaScript (ES6+), Vite |
| **Styling & Animation** | Tailwind CSS, GSAP (GreenSock), Lucide Icons |
| **State Management** | Zustand, Immer |
| **Real-Time & Networking** | Socket.IO Client, Axios |
| **Backend Runtime** | Node.js, Express 5, Socket.IO Server |
| **Security & Middleware** | Helmet, Joi, Express Mongo Sanitize, XSS-Clean, CORS |
| **Containerization & CI** | Docker, Docker Compose, Vitest, Jest, ESLint, Prettier |
| **Hosting** | Vercel (Frontend), Render / Container Host (Backend) |

---

## 🏗️ Architecture & How It Works

WebOS is designed as a decoupled client-server monorepo:

```
web-os/
├── frontend/             # React 19 + Vite client application
│   ├── src/
│   │   ├── apps/         # Individual application implementations (Terminal, Chat, IDE)
│   │   ├── components/   # Desktop, Window, Dock, and System Bar components
│   │   ├── store/        # Zustand state slices (windowManager, auth, system)
│   │   └── features/     # Feature-specific components and tests
│   └── vite.config.js
├── backend/              # Node.js + Express 5 backend server
│   ├── src/
│   │   ├── apps/         # Auth, chat socket handlers, and code runners
│   │   └── middleware/   # Security, auth, and validation middleware
│   └── envValidation.js
└── docker/               # Container configurations (dev and production)
```

### Window Management Engine
The window manager operates via a centralized Zustand store (`windowManager.js`):
1. Each application is represented as an entry with metadata (`id`, `title`, `isOpen`, `isMinimized`, `isMaximized`, `zIndex`, `coordinates`).
2. Focusing a window brings its `zIndex` to the foreground using reactive state transitions without unnecessary re-renders.
3. Drag and drop bounds are strictly calculated relative to viewport edges to prevent clipping.

---

## 📸 Screenshots

> *Recommended UI Captures:*
> 1. **Desktop Workspace:** Multi-window arrangement showing Terminal, Code IDE, and Dock.
> 2. **AI Assistant Window:** Conversation stream interacting with Gemini.
> 3. **Terminal Interface:** Running virtual commands and displaying output.
> 4. **Dock Animations:** Hover state showing icon magnification.

---

## ⚙️ Installation & Local Setup

### Prerequisites
- Node.js (v18.x or higher)
- npm or yarn
- Docker & Docker Compose (optional, for containerized run)

### 1. Clone the Repository
```bash
git clone https://github.com/muragesh46/web-os.git
cd web-os
```

### 2. Environment Configuration
Create a `.env` file in the project root based on `.env.example`:
```env
VITE_GEMINI_API_KEY=your_google_gemini_api_key
PORT=5000
NODE_ENV=development
```

### 3. Running with Docker Compose (Recommended)
```bash
docker compose -f docker/docker-compose.yml up --build
```

### 4. Running Manually

#### Frontend:
```bash
cd frontend
npm install
npm run dev
```
Open `http://localhost:5173` in your browser.

#### Backend (Optional, for real-time services):
```bash
cd backend
npm install
npm run dev
```
The backend API server boots at `http://localhost:5000`.

---

## 🧪 Testing

```bash
# Run frontend unit tests
cd frontend
npm run test

# Run backend API integration tests
cd backend
npm run test
```

---

## 🔮 Future Improvements

- [ ] Window tiling shortcuts (Snap to split left/right/quadrants).
- [ ] WebAssembly-based sandbox for isolated in-browser code execution.
- [ ] IndexedDB persistence for user files across browser sessions.
- [ ] WebRTC P2P multi-party video conferencing.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
