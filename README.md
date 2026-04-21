# 🌴 GTA VI Landing Page

<p align="center">
  <img src="public/images/photo1.webp" width="100%" alt="GTA VI Banner" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
  <img src="https://img.shields.io/badge/GSAP-88CE02?style=for-the-badge&logo=greensock&logoColor=white" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
</p>

<p align="center">
  <img src="https://img.shields.io/github/stars/salonyranjan/GTA-VI?style=social" />
  <img src="https://img.shields.io/github/forks/salonyranjan/GTA-VI?style=social" />
  <img src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" />
</p>

---

## 🚀 The Project
A high-fidelity recreation of the **Grand Theft Auto VI** landing page. This project is a deep dive into **Scroll-driven UI/UX**, utilizing GSAP's `ScrollTrigger` to create a seamless, cinematic storytelling experience in the browser.

### 🎯 Key Learning Objectives
* Mastering complex **GSAP timelines** and staggered animations.
* Implementing responsive **Tailwind CSS** layouts for media-heavy sites.
* Optimizing high-resolution `.webp` assets for performance.
---
## 🏗️ Project Architecture

To manage the high-fidelity animations and assets, the project follows a decoupled architectural pattern. This ensures that the **GSAP Animation Engine** and the **React Component Lifecycle** work in harmony without performance bottlenecks.

```mermaid
graph TD
    classDef default font-family:Arial,font-size:16px;
    classDef highlight fill:#61DAFB,stroke:#333,stroke-width:4px,color:#000;

    A[Static Assets] --> B(GSAP Animation Engine)
    B --> C{React Components}
    C --> D[Hero Section]
    C --> E[Content Section]
    C --> F[Outro Section]
    F --> G[Developed by Salony Ranjan]:::highlight
```
---

## 🏗️ Technical Implementation

The core of this project is built on the synergy between **React's component-based architecture** and **GSAP's high-performance animation engine**. Below is a breakdown of the critical implementation details.

### 🎭 Animation Orchestration
I utilized the `@gsap/react` hook to ensure animations are properly scoped and cleaned up during the component lifecycle, preventing memory leaks—a critical "industry-standard" practice.

#### Key Implementation Snippet:
```javascript
// Outro.jsx - Handling the cinematic finale
useGSAP(() => {
  // 1. Initial State Setup
  gsap.set('.final-message', { marginTop: '-100vh', opacity: 0 });

  // 2. ScrollTrigger Timeline
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: '.final-message',
      start: 'top 30%',
      end: 'top 10%',
      scrub: true, // Smoothly ties animation to scroll progress
    }
  });

  // 3. Execution
  tl.to('.final-content', { opacity: 0, duration: 1, ease: 'power1.inOut' })
    .to('.final-message', { opacity: 1, duration: 1, ease: 'power1.inOut' });
}, { scope: containerRef }); // Scoped for performance
```

---
