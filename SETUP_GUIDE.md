# 🏗️ Ntalasha Architects — Complete Setup Guide

## Quick Status

✅ **index.html** — Fixed & Renamed (compass now follows scroll)
✅ **ar-viewer.html** — Ready to use
✅ **scroll.mp3** — Generated (iPad-style click sound)

---

## 📁 Folder Structure

Your project should be organized as follows:

```
ntalasha-architects/
│
├── index.html                    ← Main website (renamed from Ntalasha_Architects__1_.html)
├── ar-viewer.html                ← AR/3D viewer (opened in pop-up window)
│
└── src/
    ├── images/
    │   ├── hero-bg.jpg           ← Hero background still
    │   ├── about-founder.jpg     ← Founder/team portrait
    │   ├── project-1.jpg         ← Residential Villa project
    │   ├── project-2.jpg         ← Corporate HQ project
    │   ├── project-3.jpg         ← Mixed-Use Development project
    │   ├── project-4.jpg         ← Institutional Complex project
    │   ├── project-5.jpg         ← Landscape Masterplan project
    │   ├── project-6.jpg         ← Interior Design Suite project
    │   ├── vr-preview.jpg        ← VR technology card background
    │   ├── ar-preview.jpg        ← AR technology card background
    │   └── zambia-map.jpg        ← Contact section map/location image
    │
    ├── video/
    │   ├── hero-reel.mp4         ← Hero section video loop (H.264)
    │   └── hero-reel.webm        ← Hero section video fallback (VP9)
    │
    ├── scroll/
    │   └── scroll.mp3            ← iPad-style scroll stop sound ✅ GENERATED
    │
    └── models/
        ├── ar1.glb               ← Residential Villa 3D model
        ├── ar2.glb               ← Corporate HQ 3D model
        └── ar3.glb               ← Mixed-Use Development 3D model
```

---

## 🖼️ Image Reference Table

| Image File | Dimensions | Usage | Location in Site | Notes |
|---|---|---|---|---|
| **hero-bg.jpg** | 1920×1080 | Hero background image | Hero Section (#hero) | Grayscale filter applied; overlaid with gradient |
| **about-founder.jpg** | 800×1100 | Founder/team photo | About Panel (#about) | Portrait crop, vertical emphasis |
| **project-1.jpg** | 800×600 | Residential Villa | Projects Grid (project-card) | First project card (top-left) |
| **project-2.jpg** | 800×600 | Corporate HQ | Projects Grid | Second project card (top-right) |
| **project-3.jpg** | 800×600 | Mixed-Use Dev | Projects Grid | Third project card (middle-left) |
| **project-4.jpg** | 800×600 | Institutional | Projects Grid | Fourth project card (middle-right) |
| **project-5.jpg** | 800×600 | Landscape Plan | Projects Grid | Fifth project card (bottom-left) |
| **project-6.jpg** | 800×600 | Interior Design | Projects Grid | Sixth project card (bottom-right) |
| **vr-preview.jpg** | 1200×900 | VR tech card background | Tech Panel (#tech) — VR card | Dark moody interior recommended |
| **ar-preview.jpg** | 1200×900 | AR tech card background | Tech Panel (#tech) — AR card | Architecture + device overlay |
| **zambia-map.jpg** | 1200×900 | Location map | Contact Panel (#contact) | Lusaka/Zambia map or architectural context |

---

## 🎬 Video Files

| Video File | Codec | Dimensions | Usage | Location | Notes |
|---|---|---|---|---|---|
| **hero-reel.mp4** | H.264 (AVC) | 1920×1080 | Hero background loop | `src/video/hero-reel.mp4` | Primary format; <8MB recommended; 30fps |
| **hero-reel.webm** | VP9 (WebM) | 1920×1080 | Hero background fallback | `src/video/hero-reel.webm` | Firefox compatibility; same content |

**Video Requirements:**
- Loop duration: 8–12 seconds (smooth transition)
- Bitrate: H.264 @ 4–6 Mbps, VP9 @ 3–4 Mbps
- Must be architecture/landscape footage
- Grayscale filter applied via CSS (don't pre-grayscale)
- Auto-plays muted, loops infinitely

---

## 🔊 Audio Files

| Audio File | Format | Bitrate | Duration | Usage | Location |
|---|---|---|---|---|---|
| **scroll.mp3** | MP3 | 56 kbps | 250ms | Scroll deceleration sound | `src/scroll/scroll.mp3` |

**Audio Details:**
- ✅ **Already Generated** — iPad-style soft thud + high-frequency click
- Triggers when scrolling motion decelerates to stop
- Falls back to Web Audio API synth if file is missing
- Volume: 0.22 (22% of max)
- Does NOT play on first scroll — only after momentum decay completes

---

## 🎮 3D Model Files (AR Viewer)

| Model File | Format | Usage | AR Viewer Dialog | Notes |
|---|---|---|---|---|
| **ar1.glb** | GLTF (Binary) | Residential Villa | Launched from project-1 card | 3D + AR mode support |
| **ar2.glb** | GLTF (Binary) | Corporate Headquarters | Launched from project-2 card | 3D + AR mode support |
| **ar3.glb** | GLTF (Binary) | Mixed-Use Development | Launched from project-3 card | 3D + AR mode support |

**Model Notes:**
- Format: GLTF 2.0 binary (.glb) — includes geometry, materials, textures
- Recommended size: < 5MB each
- AR requires WebXR-capable device (Android Chrome / iOS 15+)
- Desktop fallback: 3D orbit mode with mouse/touch controls
- Models are scaled 0.3× when placed in real-world AR

---

## 🧭 Compass (Scroll Indicator) — **FIXED**

**What was fixed:**
- **Problem:** Compass wasn't rotating with scroll position
- **Solution:** Added real-time rotation calculation in `updateUI()` function
- **How it works:**
  - Rotates 360° as you scroll from start to end
  - Uses formula: `compassRotation = (scrollProgress × 360)°`
  - Updates every frame during scroll animation
  - Fixed position: top-right corner (top: 28px, right: 48px)

**CSS Selector:** `#compass`  
**Rotation Applied Via:** `compass.style.transform = rotate(${angle}deg)`

---

## 🔊 Scroll Sound — **GENERATED**

**File Details:**
- **Format:** MP3 (44.1 kHz, 16-bit mono, 56 kbps)
- **Duration:** 250ms (0.25 seconds)
- **Size:** 2.1 KB
- **Style:** iPad-like deceleration click
- **Composition:**
  - Low-frequency thud (90 Hz → 30 Hz exponential drop over 120ms)
  - High-frequency click (3200 Hz → 800 Hz over 60ms)
  - Soft envelope (exponential fade)

**How It Triggers:**
1. User scrolls (wheel, touch, or keyboard)
2. Scroll momentum decays
3. When momentum reaches near-zero, sound plays
4. Debounced: won't play more than once per 180ms

**Fallback:**
- If `src/scroll/scroll.mp3` is missing, Web Audio API generates the same sound in real-time
- No sound failures — always works

---

## 🎯 Image Placement Map

### Hero Section
```
┌─────────────────────────────────────┐
│                                     │
│   hero-bg.jpg (full 100vw × 100vh)  │
│   + Gradient overlay                │
│   + Text content (left side)        │
│                                     │
│                                     ├─ COMPASS in top-right
│                                     │  (rotates with scroll)
└─────────────────────────────────────┘
```

### About Section
```
┌──────────────────────────────────────────────┐
│  TEXT (left)       │      about-founder.jpg  │
│  "Our Vision"      │      (40% width, fill)  │
│  Paragraph         │      vertical crop      │
│  Button            │                         │
└──────────────────────────────────────────────┘
```

### Projects Section (160vw wide)
```
┌──────────────────────────────────────────────────────┐
│ "Featured Projects"                                  │
├──────────────┬──────────────┬──────────────┐         │
│ project-1.jpg│ project-2.jpg│ project-3.jpg│ ···     │
│ (800×600)    │ (800×600)    │ (800×600)    │         │
├──────────────┼──────────────┼──────────────┤         │
│ project-4.jpg│ project-5.jpg│ project-6.jpg│ ···     │
│ (800×600)    │ (800×600)    │ (800×600)    │         │
└──────────────┴──────────────┴──────────────┘         │
```

### Technology Section
```
┌────────────────────────────────────┐
│  "Technology + Innovation"         │
├─────────────────────────────────────┤
│  VR CARD              │  AR CARD    │
│  vr-preview.jpg       │ ar-preview  │
│  (background overlay) │ .jpg (BG)   │
│  + Icon + Text        │ + Icon +    │
└────────────────────────────────────┘
```

### Contact Section
```
┌──────────────────────────────────────────────┐
│  Contact Info (left)  │  zambia-map.jpg      │
│  - Address            │  (40% width, fill)   │
│  - Phone              │  - Lusaka location   │
│  - Email              │  - Map or photo      │
│  - Hours              │                      │
└──────────────────────────────────────────────┘
```

---

## ✅ Checklist Before Launch

- [ ] **Images** — All 11 images added to `src/images/`
- [ ] **Videos** — Both hero videos in `src/video/`
- [ ] **Audio** — `scroll.mp3` in `src/scroll/` (✅ provided)
- [ ] **Models** — 3 GLB files in `src/models/`
- [ ] **HTML Files** — `index.html` and `ar-viewer.html` in root
- [ ] **Compass** — Rotates 360° during horizontal scroll
- [ ] **Scroll Sound** — Plays on scroll completion
- [ ] **Mobile Tested** — Touch scrolling works
- [ ] **AR Support Checked** — Android Chrome / iOS 15+

---

## 🚀 Quick Start

1. **Create folder structure:**
   ```bash
   mkdir -p src/images src/video src/scroll src/models
   ```

2. **Add provided files:**
   - `index.html` → root
   - `ar-viewer.html` → root
   - `scroll.mp3` → `src/scroll/` ✅ already done

3. **Add your assets:**
   - 11 JPG images → `src/images/`
   - 2 video files → `src/video/`
   - 3 GLB models → `src/models/`

4. **Test locally:**
   ```bash
   python3 -m http.server 8000
   # Open http://localhost:8000
   ```

5. **Deploy:**
   - Upload entire folder to web server
   - Ensure all paths relative to root

---

## 📝 Notes

- **Compass Now Follows Scroll** ✅
  - Real-time rotation: `rotation = (scrollPosition / maxScroll) × 360°`
  - Smooth updates every frame during momentum
  - CSS: `will-change: transform` for GPU acceleration

- **Scroll Sound Features** ✅
  - Generated iPad-style audio (2.1 KB MP3)
  - Fallback Web Audio synth if file missing
  - Soft, non-intrusive (22% volume)
  - Debounced to prevent rapid firing

- **AR Viewer**
  - Pop-up window (480×820px)
  - 3D orbit mode on desktop
  - WebXR AR on compatible mobile
  - Models scale 0.3× in real-world AR

- **Browser Support**
  - Chrome/Edge 90+
  - Firefox 88+
  - Safari 15+ (AR limited to iOS 15.1+)
  - Mobile: Android Chrome, iOS Safari

---

## 🎨 Color Palette (CSS Variables)

```css
--black:    #0a0a0a
--gray-90:  #111111
--gray-80:  #1e1e1e
--gray-60:  #3a3a3a
--gray-40:  #6b6b6b
--gray-20:  #b0b0b0
--gray-10:  #d8d8d8
--white:    #f5f5f3
--accent:   #e8e8e4
```

---

## 📧 Support

All files are ready to use. If any images or videos are missing, the site will gracefully degrade:
- Missing images → show background color
- Missing video → show fallback image
- Missing scroll sound → use Web Audio synth

**Last Updated:** May 26, 2026
