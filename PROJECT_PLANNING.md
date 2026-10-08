# Project Planning: Diet Soda 3D Interactive Website

## 1. Executive Summary
The **Diet Soda 3D Interactive Website** is a high-performance, single-page creative marketing experience showcasing a premium zero-sugar beverage line. Built with Google's `<model-viewer>` Web Component and GSAP, the landing page provides a rich, tactile 3D experience with real-time mouse interaction, dynamic lighting, fluid flavor transitions, and physics-inspired particle effects.

---

## 2. Technical Stack & Architecture
- **Core Languages**: Pure HTML5, CSS3, Modern JavaScript (ES6+).
- **3D Engine**: Google `<model-viewer>` (`@google/model-viewer/dist/model-viewer.min.js`) utilizing Three.js and WebGL under the hood.
- **Animation Framework**: GSAP 3 (`gsap.min.js`) for choreographed property tweens, background gradients, and spin transitions.
- **Typography**: Google Fonts (`Inter`, `Outfit`, `Manrope`, `Galada`).
- **Build Requirements**: Zero build tools, bundlers, or frameworks; pure self-contained browser execution.

---

## 3. Implemented Capabilities (Phase 1)
- [x] **Zero-Scroll Viewport Shell**: Fluid responsive layout designed for full viewport immersion (`100vh`, no scrollbars).
- [x] **Real-time 3D Product Can**: Centerpiece 3D can (`deit_soda2.glb`) that tilts dynamically toward cursor coordinates with smoothed linear interpolation (lerp).
- [x] **Parallax Floating Layers**:
  - Distant floating leaves (`leaves.glb`) with low-depth parallax.
  - Background berries (`cherry.glb`) with reverse parallax.
  - Foreground berries with higher depth multiplier and subtle sinusoidal bobbing.
- [x] **Cursor Repulsion Field**: 400px radius force field around the cursor pushing berries away dynamically with rotational velocity.
- [x] **Choreographed Flavor Transition**:
  - Smooth background radial gradient interpolation.
  - 720° can spin animation with simulated motion blur.
  - Real-time PBR texture swapping on the can material (`green base color.jpg` ↔ `blue base color.jpg`).
  - Implosion and explosion of berry models with model replacement (`cherry.glb` ↔ `blueberry.glb`).
- [x] **Particle Bubble Generator**: Continuous spawning of rising bubbles (`bubble.png`) with randomized drift, spin, scale, and lifespan.
- [x] **Glassmorphic UI**: Navigational pill bar and flavor cards with backdrop blur, subtle borders, and `#fbcfe8` pink accents.

---

## 4. Planned Milestones & Roadmap

### Milestone 1: Touch & Mobile Responsiveness Enhancements
- **Gyroscope & Device Orientation**:
  - Support mobile device tilt (`DeviceOrientationEvent` / `DeviceMotionEvent`) to control can orbit tilt on iOS and Android.
- **Touch Repulsion**:
  - Adapt pointer repulsion field to single-finger touch drag and touchmove events.
- **Adaptive Asset Scaling**:
  - Detect low-power devices and reduce particle/bubble count for consistent 60 FPS performance.

### Milestone 2: Additional Flavors & Customizer
- **Expanded Flavor Lineup**:
  - Add "Fiery Blood Orange" (ruby/amber theme).
  - Add "Crisp Mint Lime" (bright lime green theme).
- **Dynamic Nutrition Information Drawer**:
  - Interactive sliding drawer displaying real-time calories, ingredients, and flavor profiles per selection.
- **Audio & Sound FX**:
  - Subtle spatial audio effects: can opening click, carbonation fizz soundscape, and card selection chimes with a toggle button.

### Milestone 3: E-Commerce & Checkout Integration
- **Interactive Cart & Drawer**:
  - Quantity selector, pack size picker (6-pack, 12-pack, 24-pack).
  - Slide-out cart modal with glassmorphic aesthetic.
- **Direct Checkout API**:
  - Integration with Stripe Elements or Shopify Storefront API.

### Milestone 4: Performance & Asset Optimization
- **Asset Compression**:
  - Convert 3D `.glb` assets using Draco or Meshopt compression to minimize download size.
  - Convert texture images to `.webp` / `.avif` formats.
- **Offline / PWA Support**:
  - Service worker caching for 3D models and textures for instant repeat loads.

---

## 5. Quality Assurance & Browser Matrix
| Browser / Platform | 3D WebGL Support | GSAP Tweens | Backdrop Filter | Status |
|---|---|---|---|---|
| Chrome (Desktop) | Full | Full | Full | Verified |
| Edge (Desktop) | Full | Full | Full | Verified |
| Firefox (Desktop) | Full | Full | Full | Verified |
| Safari (macOS / iOS) | Full | Full | `-webkit-backdrop-filter` | Verified |
| Chrome / Samsung (Android) | Full | Full | Full | Planned |

---

## 6. Project Conventions & Git Workflow
- `main`: Production-ready, stable releases.
- `dev`: Active integration and feature development.
- `append`: Feature branches, planning docs, and staging iterations.
