# 📸 Image & Asset Reference — Quick Lookup

## All Images Needed (11 Total)

### ✅ Images Already Referenced in index.html

| # | File Name | Size | Location in Site | Section |
|---|-----------|------|------------------|---------|
| 1️⃣ | **hero-bg.jpg** | 1920×1080 | Full background | Hero |
| 2️⃣ | **about-founder.jpg** | 800×1100 | Right side panel | About |
| 3️⃣ | **project-1.jpg** | 800×600 | Grid position 1 | Projects |
| 4️⃣ | **project-2.jpg** | 800×600 | Grid position 2 | Projects |
| 5️⃣ | **project-3.jpg** | 800×600 | Grid position 3 | Projects |
| 6️⃣ | **project-4.jpg** | 800×600 | Grid position 4 | Projects |
| 7️⃣ | **project-5.jpg** | 800×600 | Grid position 5 | Projects |
| 8️⃣ | **project-6.jpg** | 800×600 | Grid position 6 | Projects |
| 9️⃣ | **vr-preview.jpg** | 1200×900 | VR tech card BG | Technology |
| 🔟 | **ar-preview.jpg** | 1200×900 | AR tech card BG | Technology |
| 1️⃣1️⃣ | **zambia-map.jpg** | 1200×900 | Contact map | Contact |

---

## 📁 Folder Structure for Images

```
src/
└── images/
    ├── hero-bg.jpg
    ├── about-founder.jpg
    ├── project-1.jpg
    ├── project-2.jpg
    ├── project-3.jpg
    ├── project-4.jpg
    ├── project-5.jpg
    ├── project-6.jpg
    ├── vr-preview.jpg
    ├── ar-preview.jpg
    └── zambia-map.jpg
```

---

## 🎯 Exact Paths in HTML (src attributes)

```html
<!-- HERO SECTION -->
<div class="hero-bg" style="background-image: url('src/images/hero-bg.jpg');">

<!-- ABOUT SECTION -->
<div class="panel-image" style="background-image: url('src/images/about-founder.jpg');"></div>

<!-- PROJECTS GRID (6 cards) -->
<div class="project-card" style="background-image: url('src/images/project-1.jpg');"></div>
<div class="project-card" style="background-image: url('src/images/project-2.jpg');"></div>
<div class="project-card" style="background-image: url('src/images/project-3.jpg');"></div>
<div class="project-card" style="background-image: url('src/images/project-4.jpg');"></div>
<div class="project-card" style="background-image: url('src/images/project-5.jpg');"></div>
<div class="project-card" style="background-image: url('src/images/project-6.jpg');"></div>

<!-- TECHNOLOGY CARDS -->
<div class="tech-card" style="background-image: url('src/images/vr-preview.jpg');"></div>
<div class="tech-card" style="background-image: url('src/images/ar-preview.jpg');"></div>

<!-- CONTACT SECTION -->
<div class="contact-map" style="background-image: url('src/images/zambia-map.jpg');"></div>
```

---

## 🎬 Video Files Location

```
src/
└── video/
    ├── hero-reel.mp4      ← H.264 codec (primary)
    └── hero-reel.webm     ← VP9 codec (fallback)
```

**HTML Reference:**
```html
<video class="hero-video" autoplay muted loop playsinline 
       src="src/video/hero-reel.mp4" 
       type="video/mp4"></video>
```

---

## 🎮 3D Model Files Location

```
src/
└── models/
    ├── ar1.glb    ← Residential Villa
    ├── ar2.glb    ← Corporate HQ
    └── ar3.glb    ← Mixed-Use Development
```

**Triggered by:**
- `launchAR('ar1', 'Residential Villa')` → opens ar-viewer.html with ar1.glb
- `launchAR('ar2', 'Corporate HQ')` → opens ar-viewer.html with ar2.glb
- `launchAR('ar3', 'Mixed-Use Development')` → opens ar-viewer.html with ar3.glb

---

## 🔊 Audio Files Location

```
src/
└── scroll/
    └── scroll.mp3    ✅ Already provided (iPad scroll sound)
```

**Features:**
- ✅ Generated iPad-style click
- Format: MP3 (56 kbps, 44.1 kHz, 250ms)
- Plays on scroll deceleration
- Fallback: Web Audio API synth

---

## 📍 Page Section Map

### Horizontal Scroll Order

```
1. HERO (100vw)
   ├─ hero-bg.jpg
   ├─ hero-video (mp4/webm)
   └─ Compass indicator 🧭 (rotates with scroll)

2. ABOUT (100vw)
   ├─ about-founder.jpg
   └─ Text + Button

3. PROJECTS (160vw — WIDE)
   ├─ project-1.jpg
   ├─ project-2.jpg
   ├─ project-3.jpg
   ├─ project-4.jpg
   ├─ project-5.jpg
   └─ project-6.jpg

4. TECHNOLOGY (100vw)
   ├─ vr-preview.jpg (background)
   └─ ar-preview.jpg (background)

5. CONTACT (100vw)
   └─ zambia-map.jpg
```

---

## 🖼️ Image Recommendations

| Image | Content | Style | Notes |
|-------|---------|-------|-------|
| **hero-bg.jpg** | Exterior landscape / aerial shot | Architectural photography | Will be grayscale + gradient overlay |
| **about-founder.jpg** | Portrait / team photo | Professional headshot | Tall crop (800×1100) — face near top |
| **project-*.jpg** | Finished architecture / renderings | Professional photography | 6 diverse project examples |
| **vr-preview.jpg** | Moody interior / tech environment | Dark, atmospheric | Used as subtle background overlay |
| **ar-preview.jpg** | Building + device visualization | Tech-forward | Phone mockup or building overlay concept |
| **zambia-map.jpg** | Lusaka location map or city view | Geographic/contextual | Shows location of firm |

---

## ⚡ Performance Tips

1. **Optimize Images:**
   - Use WebP format for smaller file size
   - Provide JPEG fallback
   - Keep hero-bg.jpg under 300KB
   - Keep project images under 200KB each

2. **Video:**
   - Hero video < 8MB (H.264 4-6 Mbps)
   - Encode in both MP4 + WebM formats
   - 30fps, 1920×1080, 8-12 second duration

3. **Models:**
   - Keep GLB files under 5MB each
   - Optimize polygon count for mobile AR
   - Include materials and lighting

---

## 🧪 Test Checklist

- [ ] All 11 images load without errors
- [ ] Hero video plays and loops smoothly
- [ ] Compass rotates 360° as you scroll ✅
- [ ] Scroll sound plays on momentum stop ✅
- [ ] AR/3D models open in pop-up window
- [ ] Mobile touch scrolling works
- [ ] Responsive layout on tablet/mobile
- [ ] No console errors in DevTools

---

## ❌ Fallbacks (Graceful Degradation)

If files are missing:
- **Missing images** → Background color shows instead
- **Missing video** → Hero image stays visible
- **Missing scroll.mp3** → Web Audio synth plays instead
- **Missing models** → Error message in pop-up window

**No files are required to cause page failure** — site degrades gracefully.

---

## 📋 Copy-Paste File List

Save this as your shopping list:

```
Images (11 files):
□ hero-bg.jpg
□ about-founder.jpg
□ project-1.jpg
□ project-2.jpg
□ project-3.jpg
□ project-4.jpg
□ project-5.jpg
□ project-6.jpg
□ vr-preview.jpg
□ ar-preview.jpg
□ zambia-map.jpg

Videos (2 files):
□ hero-reel.mp4
□ hero-reel.webm

Models (3 files):
□ ar1.glb
□ ar2.glb
□ ar3.glb

Audio (1 file):
✅ scroll.mp3 (provided)
```

---

**Ready to Use:** index.html, ar-viewer.html, scroll.mp3 ✅
