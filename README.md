# Personal Standard — Interactive 3D Portfolio

[![Three.js](https://img.shields.io/badge/Three.js-r139-black?logo=three.js)](https://threejs.org/)
[![WebGL](https://img.shields.io/badge/WebGL-2.0-red?logo=webgl)](https://www.khronos.org/webgl/)
[![GSAP](https://img.shields.io/badge/GSAP-3.x-green?logo=greensock)](https://greensock.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> A modern, interactive 3D WebGL portfolio website engineered with **Three.js**, **GSAP**, custom **Blender 3D** models, spatial audio, and responsive SVG HUD data visualization.

---

## 📸 Preview

[![Personal Standard 3D Portfolio Preview](https://i.postimg.cc/0NkC1C0Y/Screenshot-2024-06-04-102859.png)](https://postimg.cc/cvz3QwjC)

---

## ✨ Key Features

- **Isometric 3D Room & Lab Worlds**:
  - Fully baked lighting and shadow maps created in Blender.
  - Interactive 3D character with animated face expressions (idle, blink, smile, startled, sleepy).
  - Smooth camera transitions across 3D waypoints as the user scrolls.

- **Dynamic Sound Engine**:
  - Immersive background ambience for both the room and lab environments.
  - Micro-interaction audio effects: mechanical keyboard typing, mouse clicks, transitions, bubble pops, and sound toggle controls.

- **Futuristic HUD & SVG Visualizations**:
  - Custom SVG clipping paths, gradients, and animated cyber-aesthetic skill meters.
  - Interactive journey cards detailing experience, skills, and creative background.

- **3D Work / Portfolio Carousel**:
  - Perspective-transformed card deck showcasing featured web applications, tools, and games.
  - Instant direct links to live deployments and source repositories.

- **Interactive Contact Portal**:
  - 3D character contact scene with real-time form validation (name, email, message length checks).
  - Animated delivery feedback with SVG success/error line strokes and offline/static fallback support.
  - Primary and alternative contact details displayed directly.

- **Fully Responsive Architecture**:
  - Dynamic camera waypoint recalculation for portrait and landscape aspect ratios.
  - Touch-friendly swipe gestures and mouse wheel navigation.

---

## 🛠️ Tech Stack

| Domain | Technology / Library |
| --- | --- |
| **Core 3D Engine** | [Three.js](https://threejs.org/) (WebGL Renderer, GLTFLoader, OrbitControls, Raycaster) |
| **Animation & Easing** | [GSAP](https://greensock.com/) (GreenSock Animation Platform) |
| **3D Modeling & Baking** | Blender (Low-poly GLB models, baked diffuse & shadow textures) |
| **UI & Styling** | HTML5, CSS3 (Aspect-ratio media queries, Custom Properties), Scalable Vector Graphics (SVG) |
| **Audio** | HTML5 Audio / Spatial audio controllers |
| **Architecture** | Native ES6 Modules (Zero heavy build step required for deployment) |

---

## 📁 Project Structure

```text
Personal-Standard/
├── index.html                   # Main HTML shell, SVG definitions, and DOM overlay
├── index.css                    # Comprehensive styling, responsive layouts & animations
├── index.js                     # Three.js scene graph, GSAP timelines, audio & state logic
├── README.md                    # Project documentation
├── touch-icon.png               # Mobile web app touch icon
├── skills-profile-picture.png   # Avatar graphic for skills HUD
├── poppins-*.woff2              # Self-hosted typography
├── icons/                       # Pixel art and social media vector icons
│   ├── github-icon.png
│   ├── linkedin-icon.png
│   ├── mail-icon.png
│   ├── twitter-icon.png
│   └── ...
├── images/                      # Award badges, textures, and project mockups
│   ├── cssda-icon.png
│   ├── david1.png
│   └── projects/                # Portfolio showcase screenshot assets
├── models/                      # 3D GLTF/GLB models & baked texture maps
│   ├── character/               # Character body, baked head, and facial expression textures
│   ├── room/                    # Isometric room mesh, baked lightmaps, desktop screens
│   ├── lab/                     # Science lab mesh, tubes, and screen textures
│   └── contact/                 # Contact scene mesh and shadow planes
├── sounds/                      # Ambient soundscapes & interactive audio SFX (.mp3)
└── textures/                    # Matcaps, bubble sprites, and particles
```

---

## 🚀 Getting Started

Because the project loads 3D `.glb` models, audio files, and uses native ES6 JavaScript modules, it must be served through an HTTP/HTTPS local server (browsers restrict `file://` access to local assets for CORS security).

### Option 1: Using Node.js (npx)

```bash
# Serve current directory using npx serve
npx serve .
```

### Option 2: Using Python

```bash
# Python 3.x
python -m http.server 8000
```
Then visit `http://localhost:8000` in your web browser.

### Option 3: Using VS Code Live Server

1. Open the project folder in **Visual Studio Code**.
2. Install the **Live Server** extension.
3. Click **"Go Live"** in the bottom status bar.

---

## 📬 Contact & Brand Details

**Personal Standard** is open for creative engineering collaborations, freelance opportunities, and interactive web projects.

- **Brand**: Personal Standard
- **Primary Email**: [contact@personalstandard.com](mailto:contact@personalstandard.com)
- **Alternative Email**: [info@personalstandard.com](mailto:info@personalstandard.com)
- **GitHub**: [github.com/personalstandard](https://github.com/personalstandard)
- **LinkedIn**: [linkedin.com/company/personal-standard](https://www.linkedin.com/company/personal-standard)
- **Twitter / X**: [@PersonalStandard](https://twitter.com/personalstandard)

---

## ⚙️ Configuration & Customization

### Adding / Editing Portfolio Projects
All showcase cards are configured in `index.js` inside the `oM` array (around line ~24196):

```javascript
const oM = [
    {
        id: 0,
        name: "Project Name",
        description: "Short project summary",
        image: "images/projects/your-project.jpg",
        tags: ["javascript", "backend", "html", "css"],
        liveview: "https://your-live-demo.com",
        github: "https://github.com/personalstandard/your-repo",
        alt: "Project preview"
    },
    // ...
];
```

### Connecting the Contact Form to a Backend
In `index.js`, the `sendMail()` method dispatches a `POST` request to `/api/contact`. You can connect this to:
- A serverless function (AWS Lambda, Vercel Serverless, Netlify Functions).
- A 3rd-party form handler such as [Formspree](https://formspree.io/) or [EmailJS](https://www.emailjs.com/).

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
Feel free to use and adapt it for your personal or commercial interactive portfolios.
