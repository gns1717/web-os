# WebOS — Browser-Based Desktop Operating System

[![Live Demo](https://img.shields.io/badge/Live_Demo-web--os--beta--two.vercel.app-blue?style=flat-square&logo=vercel)](https://web-os-beta-two.vercel.app)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-6.x-646CFF?style=flat-square&logo=vite)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.x-38B2AC?style=flat-square&logo=tailwind-css)](https://tailwindcss.com/)
[![Zustand](https://img.shields.io/badge/State-Zustand-orange?style=flat-square)](https://github.com/pmndrs/zustand)
[![Node.js & Express](https://img.shields.io/badge/Backend-Express_5_%26_Socket.IO-black?style=flat-square&logo=express)](https://expressjs.com/)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=flat-square&logo=docker)](https://www.docker.com/)

An interactive, high-performance web desktop operating system environment engineered with React 19, Vite, Tailwind CSS, GSAP, and a real-time Express & Socket.IO backend. WebOS simulates a native multi-window desktop interface entirely in modern web browsers.

---

Live Demo: https://web-os-beta-two.vercel.app
Repository: https://github.com/gns1717/web-os

---

## 📌 Overview

Traditional web applications often rely on page-by-page navigation. WebOS explores a different approach by turning the browser viewport into a desktop-style workspace.

Users can interact with multiple application windows, navigate a virtual filesystem, use a terminal-style interface, edit code, and access an AI assistant powered by the Google Gemini API.

## ✨ Key Features

### 🖥️ Desktop & Window Management

- **Draggable and resizable windows** with minimize, maximize, and restore interactions.
- **macOS-inspired dock** with animated icon interactions.
- **System navigation bar** with a clock, application indicators, and system controls.
- **Multi-window workspace** designed for desktop-style multitasking.

### 📦 Built-In Applications

- **AI Assistant:** A conversational interface powered by the Google Gemini API.
- **Terminal Emulator:** A virtual command-line interface for filesystem navigation and simulated system commands.
- **Code Studio:** An in-browser code editing environment.
- **File Explorer:** Browse a hierarchical virtual filesystem.
- **Media Viewers:** View supported PDF documents and images.
- **Productivity Utilities:** Calculator, calendar, notes, and weather interfaces.

### ⚡ Backend & Testing

- **Real-time communication:** Socket.IO for supported messaging and signaling features.
- **API protection:** Middleware for request validation, security headers, and rate limiting.
- **Testing support:** Frontend and backend test suites using the tools configured in the project.
- **Containerization:** Docker and Docker Compose configurations, where supported by the repository.

---

## 🛠️ Tech Stack

| Layer                   | Technologies                                          |
| ----------------------- | ----------------------------------------------------- |
| Frontend                | React 19, JavaScript, Vite                            |
| Styling & Animation     | Tailwind CSS, GSAP, Lucide Icons                      |
| State Management        | Zustand, Immer                                        |
| Networking              | Axios, Socket.IO Client                               |
| Backend                 | Node.js, Express 5, Socket.IO                         |
| Security                | Helmet, Joi, CORS, configured sanitization middleware |
| Testing & Code Quality  | Vitest, Jest, Supertest, ESLint, Prettier             |
| Deployment & Containers | Vercel, Docker, Docker Compose                        |

*Technology versions and package availability should be confirmed against the current project configuration.*

---

## 🏗️ Architecture

WebOS separates the browser interface from backend services.

```text
web-os/
├── frontend/
│   ├── src/
│   │   ├── apps/
│   │   ├── components/
│   │   ├── store/
│   │   └── features/
│   └── vite.config.js
├── backend/
│   └── src/
│       ├── apps/
│       └── middleware/
└── docker/
```

*Illustrative structure: actual directories may differ in this repository.*

### Window Management

The window management system coordinates the state of open applications.

1. Each window maintains properties such as its title, position, visibility, and active state.
2. Focusing a window brings it to the foreground.
3. Window interactions update the desktop state.
4. Dragging and resizing allow users to arrange applications within the workspace.

Zustand is used for centralized state management where implemented in the codebase.

---

## 📸 Screenshots

Screenshots can be added here to demonstrate the interface:

- Desktop workspace with multiple windows.
- AI assistant conversation.
- Terminal and code editor.
- Dock animations and system navigation bar.

To add a screenshot, save it in the repository (for example, `docs/images/desktop.png`) and reference it in Markdown:

```markdown
![WebOS Desktop](docs/images/desktop.png)
```

---

## ⚙️ Installation & Local Setup

### Prerequisites

- Node.js version compatible with the project.
- npm or the package manager specified by the lockfile.
- Docker and Docker Compose if using the container configuration.

### 1. Clone This Repository

```bash
git clone https://github.com/gns1717/web-os.git
cd web-os
```

### 2. Configure Environment Variables

Check the provided environment example and backend configuration to identify the required variables.

Create the appropriate local `.env` file and add your own credentials where needed. For example:

```env
PORT=5000
NODE_ENV=development
```

Add the Gemini API key only under the variable name expected by the application. Do not commit real API keys or secrets.

### 3. Run with Docker

If the included Compose configuration is present and configured:

```bash
docker compose -f docker/docker-compose.yml up --build
```

### 4. Run Manually

**Frontend**

```bash
cd frontend
npm install
npm run dev
```

Open the local URL displayed in the terminal.

**Backend**

In a separate terminal:

```bash
cd backend
npm install
npm run dev
```

The backend port and available scripts depend on the current configuration.

---

## 🧪 Testing

Run the test commands configured in the relevant `package.json` files.

For example, if the frontend defines a `test` script:

```bash
cd frontend
npm run test
```

For the backend:

```bash
cd backend
npm run test
```

Check the scripts before running these commands, as names can vary by project configuration.

---

## 🔮 Future Improvements

- [ ] Add keyboard shortcuts and window tiling.
- [ ] Improve accessibility and responsive layouts.
- [ ] Explore persistence for user files and desktop preferences.
- [ ] Strengthen automated test coverage.
- [ ] Improve error handling and loading states.
- [ ] Expand documentation for architecture and deployment.

---

## 📄 License & Attribution

This repository is based on the original project by **Muragesh Mirje**.

- **Original repository:** [https://github.com/muragesh46/web-os](https://github.com/muragesh46/web-os)
- **Current repository:** [https://github.com/gns1717/web-os](https://github.com/gns1717/web-os)

Please review the original license and preserve required notices and attribution. Any additional features, fixes, and improvements should be documented as they are implemented.

## 👨‍💻 Maintainer

**Gaurav N S**

GitHub: [@gns1717](https://github.com/gns1717)