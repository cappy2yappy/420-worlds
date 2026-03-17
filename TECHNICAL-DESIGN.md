# 420 Zone Tracker – Technical UI/UX Spec

**Version:** 1.0  
**Last Updated:** March 17, 2026  
**Source:** Alex (Product Owner)  
**Status:** OFFICIAL ART DIRECTION

---

## 1. Visual Identity & Art Direction

### Core Aesthetic
**Art Style:** "Grungy Chibi Anime" (Inspired by Gorillaz/Jamie Hewlett)

**Visual Principles:**
- High-contrast linework
- Urban "street" textures (rust, concrete, graffiti)
- Neon green accents (#42FF42)
- Character-driven UI
- Centered avatar with circular navigation

### Key Colors (CSS Variables)

```css
:root {
  /* Primary */
  --color-blaze-green: #42FF42;
  --color-neon-green: #42FF42;
  
  /* Backgrounds */
  --color-deep-charcoal: #1A1A1A;
  --color-muted-purple: #2D1B33;
  --color-rust-orange: #8B4513;
  
  /* Accents */
  --color-cyberpunk-blue: #00F2FF;
  --color-industrial-yellow: #FFD700;
  
  /* Grays */
  --color-concrete: #808080;
  --color-asphalt: #404040;
}
```

### Typography Stack

```css
:root {
  --font-display: 'Bebas Neue', 'Impact', sans-serif; /* Headers, titles */
  --font-body: 'Inter', 'Roboto', sans-serif; /* Body text */
  --font-mono: 'Space Mono', 'Courier New', monospace; /* Timers, stats */
}
```

### Texture System
- **Rust:** Noise overlay with `mix-blend-mode: multiply`
- **Concrete:** Subtle grain pattern, 2-5% opacity
- **Graffiti:** SVG overlays with `filter: drop-shadow()`

---

## 2. Component Architecture

### A. The "Global Circle" (Main Dashboard)

#### The Ring: Circular Time Zone Indicator

**Technical Spec:**
```html
<div class="global-circle">
  <svg class="timezone-ring" viewBox="0 0 400 400">
    <defs>
      <linearGradient id="blaze-gradient">
        <stop offset="0%" stop-color="#42FF42" />
        <stop offset="100%" stop-color="#FFD700" />
      </linearGradient>
    </defs>
    
    <!-- 24 time zone segments -->
    <circle 
      cx="200" 
      cy="200" 
      r="180" 
      fill="none" 
      stroke="url(#blaze-gradient)" 
      stroke-width="8"
      stroke-dasharray="5 5"
    />
  </svg>
  
  <div class="avatar-center">
    <!-- Avatar canvas or PNG -->
  </div>
</div>
```

**CSS Implementation:**
```css
.global-circle {
  position: relative;
  width: 400px;
  height: 400px;
  margin: 0 auto;
}

.timezone-ring {
  position: absolute;
  top: 0;
  left: 0;
  animation: rotate 60s linear infinite;
}

@keyframes rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.timezone-ring circle {
  stroke-dasharray: 1131; /* 2πr = circumference */
  stroke-dashoffset: 0;
  transition: stroke-dashoffset 0.5s ease;
}

/* Dynamic highlighting via conic-gradient */
.timezone-ring--active {
  background: conic-gradient(
    from 0deg at 50% 50%,
    transparent 0deg,
    #42FF42 15deg,
    transparent 30deg
  );
}
```

**JavaScript Logic:**
```javascript
function updateTimezoneRing() {
  const now = new Date();
  const minutes = now.getHours() * 60 + now.getMinutes();
  const targetMinutes = 16 * 60 + 20; // 4:20 PM
  
  // Calculate degrees for current timezone
  const degrees = ((minutes / 1440) * 360) % 360;
  
  // Highlight closest timezone to 4:20
  const closestZone = findClosestTimezone(degrees);
  highlightZone(closestZone);
}
```

**Dynamic Highlighting:**
- Use `conic-gradient` to highlight the zone closest to 4:20
- Rotate gradient to match current time
- Pulse animation when approaching 4:20 (within 15 minutes)

**The Avatar (Center):**
```css
.avatar-center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 200px;
  height: 200px;
  transition: transform 0.3s ease;
}

.avatar-center:hover {
  transform: translate(-50%, -50%) scale(1.1);
  cursor: pointer;
}

.avatar-center canvas {
  border-radius: 50%;
  box-shadow: 0 0 30px rgba(66, 255, 66, 0.5);
}
```

---

### B. "The 420 Studio" (Customization Engine)

#### Modular Slots System

**JSON-Driven Inventory Structure:**

```json
{
  "head": [
    {
      "id": "beanie_01",
      "name": "Black Beanie",
      "rarity": "common",
      "asset": "assets/head/beanie_01.png",
      "unlocked": true
    },
    {
      "id": "snapback_420",
      "name": "420 Snapback",
      "rarity": "rare",
      "asset": "assets/head/snapback_420.png",
      "unlocked": false
    }
  ],
  "body": [
    {
      "id": "skater_tee",
      "name": "Skater Tee",
      "rarity": "common",
      "asset": "assets/body/skater_tee.png",
      "unlocked": true
    },
    {
      "id": "leather_jacket",
      "name": "Leather Jacket",
      "rarity": "epic",
      "asset": "assets/body/leather_jacket.png",
      "unlocked": false
    }
  ],
  "stance": [
    {
      "id": "idle_skating",
      "name": "Skating Idle",
      "animation": "skating_loop.json",
      "unlocked": true
    },
    {
      "id": "idle_meditating",
      "name": "Meditating",
      "animation": "meditate_loop.json",
      "unlocked": false
    }
  ],
  "background": [
    {
      "id": "subway_grungy",
      "name": "Subway (Grungy)",
      "asset": "assets/bg/subway.png",
      "texture": "rust",
      "unlocked": true
    },
    {
      "id": "beach_chill",
      "name": "Beach (Chill)",
      "asset": "assets/bg/beach.png",
      "texture": "sand",
      "unlocked": false
    },
    {
      "id": "space_trippy",
      "name": "Space (Trippy)",
      "asset": "assets/bg/space.png",
      "texture": "stars",
      "unlocked": false
    }
  ]
}
```

**Component Structure:**

```html
<div class="studio-420">
  <div class="studio-preview">
    <canvas id="avatarPreview" width="512" height="512"></canvas>
  </div>
  
  <div class="studio-slots">
    <div class="slot-category" data-category="head">
      <h3>🎩 Head</h3>
      <div class="slot-grid" id="headSlots"></div>
    </div>
    
    <div class="slot-category" data-category="body">
      <h3>👕 Body</h3>
      <div class="slot-grid" id="bodySlots"></div>
    </div>
    
    <div class="slot-category" data-category="stance">
      <h3>🕺 Stance</h3>
      <div class="slot-grid" id="stanceSlots"></div>
    </div>
    
    <div class="slot-category" data-category="background">
      <h3>🌆 Background</h3>
      <div class="slot-grid" id="backgroundSlots"></div>
    </div>
  </div>
</div>
```

**CSS for Slot Grid:**

```css
.studio-420 {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 20px;
  padding: 20px;
  background: var(--color-deep-charcoal);
}

.studio-preview {
  position: sticky;
  top: 20px;
  height: fit-content;
}

.studio-preview canvas {
  width: 100%;
  border-radius: 15px;
  border: 3px solid var(--color-blaze-green);
  box-shadow: 0 0 40px rgba(66, 255, 66, 0.3);
}

.slot-category {
  background: rgba(45, 27, 51, 0.5);
  border: 2px solid var(--color-muted-purple);
  border-radius: 10px;
  padding: 20px;
  margin-bottom: 20px;
}

.slot-category h3 {
  font-family: var(--font-display);
  color: var(--color-blaze-green);
  margin-bottom: 15px;
  font-size: 1.5em;
}

.slot-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
  gap: 10px;
}

.slot-item {
  aspect-ratio: 1;
  background: rgba(0, 0, 0, 0.5);
  border: 2px solid rgba(255, 255, 255, 0.2);
  border-radius: 8px;
  cursor: pointer;
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
}

.slot-item:hover {
  border-color: var(--color-blaze-green);
  transform: scale(1.05);
}

.slot-item.locked {
  opacity: 0.4;
  cursor: not-allowed;
}

.slot-item.locked::after {
  content: "🔒";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 2em;
}

.slot-item.active {
  border-color: var(--color-industrial-yellow);
  box-shadow: 0 0 15px rgba(255, 215, 0, 0.5);
}

.slot-item img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

/* Rarity borders */
.slot-item[data-rarity="common"] {
  border-color: rgba(255, 255, 255, 0.3);
}

.slot-item[data-rarity="uncommon"] {
  border-color: rgba(0, 255, 0, 0.5);
}

.slot-item[data-rarity="rare"] {
  border-color: rgba(0, 136, 255, 0.5);
}

.slot-item[data-rarity="epic"] {
  border-color: rgba(160, 32, 240, 0.5);
}

.slot-item[data-rarity="legendary"] {
  border-color: rgba(255, 128, 0, 0.5);
  animation: legendary-pulse 2s ease-in-out infinite;
}

@keyframes legendary-pulse {
  0%, 100% { box-shadow: 0 0 10px rgba(255, 128, 0, 0.5); }
  50% { box-shadow: 0 0 30px rgba(255, 128, 0, 0.8); }
}
```

**JavaScript for Slot System:**

```javascript
class Studio420 {
  constructor() {
    this.inventory = {}; // Load from localStorage or API
    this.equipped = {
      head: null,
      body: null,
      stance: null,
      background: null
    };
    this.canvas = document.getElementById('avatarPreview');
    this.ctx = this.canvas.getContext('2d');
  }
  
  async loadInventory() {
    const response = await fetch('/api/inventory.json');
    this.inventory = await response.json();
    this.renderSlots();
  }
  
  renderSlots() {
    ['head', 'body', 'stance', 'background'].forEach(category => {
      const grid = document.getElementById(`${category}Slots`);
      grid.innerHTML = '';
      
      this.inventory[category].forEach(item => {
        const slotDiv = document.createElement('div');
        slotDiv.className = 'slot-item';
        slotDiv.dataset.id = item.id;
        slotDiv.dataset.rarity = item.rarity;
        
        if (!item.unlocked) {
          slotDiv.classList.add('locked');
        }
        
        if (this.equipped[category] === item.id) {
          slotDiv.classList.add('active');
        }
        
        if (item.asset) {
          const img = document.createElement('img');
          img.src = item.asset;
          img.alt = item.name;
          slotDiv.appendChild(img);
        }
        
        slotDiv.addEventListener('click', () => {
          if (item.unlocked) {
            this.equipItem(category, item.id);
          }
        });
        
        grid.appendChild(slotDiv);
      });
    });
  }
  
  equipItem(category, itemId) {
    this.equipped[category] = itemId;
    this.renderAvatar();
    this.renderSlots(); // Update active state
  }
  
  renderAvatar() {
    this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height);
    
    // Layer order: background → body → head → stance overlay
    const layers = ['background', 'body', 'head', 'stance'];
    
    layers.forEach(category => {
      const itemId = this.equipped[category];
      if (itemId) {
        const item = this.inventory[category].find(i => i.id === itemId);
        if (item && item.asset) {
          const img = new Image();
          img.src = item.asset;
          img.onload = () => {
            this.ctx.drawImage(img, 0, 0, this.canvas.width, this.canvas.height);
          };
        }
      }
    });
  }
}

// Initialize
const studio = new Studio420();
studio.loadInventory();
```

---

### C. Face-Upload (Optional Feature)

**Canvas API Integration:**

```javascript
class FaceUpload {
  constructor(canvas) {
    this.canvas = canvas;
    this.ctx = canvas.getContext('2d');
  }
  
  async uploadFace(file) {
    return new Promise((resolve, reject) => {
      const reader = new FileReader();
      
      reader.onload = (e) => {
        const img = new Image();
        img.onload = () => {
          // Overlay user face onto chibi head template
          const faceOverlay = this.createFaceOverlay(img);
          resolve(faceOverlay);
        };
        img.onerror = reject;
        img.src = e.target.result;
      };
      
      reader.onerror = reject;
      reader.readAsDataURL(file);
    });
  }
  
  createFaceOverlay(userImage) {
    // Create temporary canvas for face processing
    const tempCanvas = document.createElement('canvas');
    const tempCtx = tempCanvas.getContext('2d');
    tempCanvas.width = 512;
    tempCanvas.height = 512;
    
    // Load chibi head template
    const template = new Image();
    template.src = 'assets/templates/chibi_head_template.png';
    
    template.onload = () => {
      // Draw template
      tempCtx.drawImage(template, 0, 0, 512, 512);
      
      // Apply user face with overlay blending
      tempCtx.globalCompositeOperation = 'overlay';
      tempCtx.globalAlpha = 0.7;
      
      // Position face in the "face zone" (centered oval)
      const faceZone = {
        x: 156,
        y: 128,
        width: 200,
        height: 256
      };
      
      tempCtx.drawImage(
        userImage,
        faceZone.x,
        faceZone.y,
        faceZone.width,
        faceZone.height
      );
      
      // Reset composite
      tempCtx.globalCompositeOperation = 'source-over';
      tempCtx.globalAlpha = 1.0;
      
      // Convert to data URL
      return tempCanvas.toDataURL('image/png');
    };
  }
}
```

**HTML Integration:**

```html
<div class="face-upload-section">
  <h3>Upload Your Face (Optional)</h3>
  <input type="file" id="faceUpload" accept="image/*" />
  <button onclick="applyFaceUpload()">Apply Face</button>
  <p class="note">Your face will be overlaid on the chibi head template</p>
</div>
```

---

## 3. Asset Requirements

### File Structure

```
assets/
├── head/
│   ├── beanie_01.png
│   ├── snapback_420.png
│   ├── bandana_red.png
│   └── ... (420+ items total)
├── body/
│   ├── skater_tee.png
│   ├── leather_jacket.png
│   ├── hoodie_black.png
│   └── ...
├── stance/
│   ├── skating_loop.json (Lottie animation)
│   ├── meditate_loop.json
│   └── ...
├── backgrounds/
│   ├── subway_grungy.png
│   ├── beach_chill.png
│   ├── space_trippy.png
│   └── ...
├── templates/
│   ├── chibi_head_template.png
│   ├── body_base_male.png
│   ├── body_base_female.png
│   └── body_base_neutral.png
└── textures/
    ├── rust_overlay.png
    ├── concrete_grain.png
    └── graffiti_splatter.svg
```

### Asset Specifications

**Resolution:**
- Head items: 512×512 PNG (transparent background)
- Body items: 512×768 PNG (transparent background)
- Backgrounds: 1920×1080 PNG (full bleed)
- Textures: 512×512 PNG (tileable)

**Color Mode:** RGB (for web)  
**Bit Depth:** 8-bit  
**Compression:** PNG-8 for most, PNG-24 for gradients

**Naming Convention:**
```
{category}_{descriptor}_{variant}.png

Examples:
head_beanie_black.png
body_jacket_leather_brown.png
bg_subway_rusty_01.png
```

---

## 4. Animation System

### Idle Stance Animations

**Lottie JSON Format:**

```json
{
  "v": "5.7.4",
  "fr": 30,
  "ip": 0,
  "op": 90,
  "w": 512,
  "h": 768,
  "nm": "Skating Idle",
  "layers": [
    {
      "ty": 2,
      "nm": "Body",
      "ks": {
        "p": {
          "a": 1,
          "k": [
            { "t": 0, "s": [256, 384] },
            { "t": 45, "s": [256, 390] },
            { "t": 90, "s": [256, 384] }
          ]
        }
      }
    }
  ]
}
```

**Integration:**

```javascript
import lottie from 'lottie-web';

function playStanceAnimation(animationPath) {
  lottie.loadAnimation({
    container: document.getElementById('avatarPreview'),
    renderer: 'canvas',
    loop: true,
    autoplay: true,
    path: animationPath
  });
}
```

---

## 5. Responsive Breakpoints

```css
/* Mobile-first approach */
:root {
  --ring-size: 300px;
  --avatar-size: 150px;
}

@media (min-width: 768px) {
  :root {
    --ring-size: 400px;
    --avatar-size: 200px;
  }
}

@media (min-width: 1200px) {
  :root {
    --ring-size: 500px;
    --avatar-size: 250px;
  }
}
```

---

## 6. Performance Optimization

### Image Loading Strategy

```javascript
// Lazy load assets
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const img = entry.target;
      img.src = img.dataset.src;
      observer.unobserve(img);
    }
  });
});

document.querySelectorAll('.slot-item img').forEach(img => {
  observer.observe(img);
});
```

### Canvas Optimization

```javascript
// Use offscreen canvas for composition
const offscreen = new OffscreenCanvas(512, 512);
const offscreenCtx = offscreen.getContext('2d');

function renderAvatarOptimized() {
  // Render all layers on offscreen canvas
  offscreenCtx.clearRect(0, 0, 512, 512);
  
  // Draw layers...
  
  // Transfer to visible canvas in one operation
  ctx.drawImage(offscreen, 0, 0);
}
```

---

## 7. Accessibility

```html
<!-- Semantic HTML -->
<nav aria-label="Time zone navigation">
  <div class="global-circle" role="region" aria-label="Current time zones">
    <!-- ... -->
  </div>
</nav>

<!-- Keyboard navigation -->
<div class="slot-item" 
     tabindex="0" 
     role="button" 
     aria-label="Black Beanie - Common rarity"
     onkeypress="handleKeyPress(event)">
</div>
```

```css
/* Focus states */
.slot-item:focus {
  outline: 3px solid var(--color-blaze-green);
  outline-offset: 2px;
}

/* Reduced motion support */
@media (prefers-reduced-motion: reduce) {
  .timezone-ring {
    animation: none;
  }
  
  .legendary-pulse {
    animation: none;
  }
}
```

---

## 8. State Management

```javascript
class AppState {
  constructor() {
    this.user = {
      id: null,
      avatar: {
        head: null,
        body: null,
        stance: null,
        background: null
      },
      inventory: [],
      points: 420,
      streak: 0
    };
    
    this.loadState();
  }
  
  loadState() {
    const saved = localStorage.getItem('420_app_state');
    if (saved) {
      Object.assign(this.user, JSON.parse(saved));
    }
  }
  
  saveState() {
    localStorage.setItem('420_app_state', JSON.stringify(this.user));
  }
  
  updateAvatar(category, itemId) {
    this.user.avatar[category] = itemId;
    this.saveState();
    this.emit('avatar-updated');
  }
}

// Singleton instance
const appState = new AppState();
```

---

## 9. Build Pipeline

```json
{
  "scripts": {
    "build": "npm run build:css && npm run build:js && npm run optimize:assets",
    "build:css": "postcss src/styles.css -o dist/styles.min.css",
    "build:js": "webpack --mode production",
    "optimize:assets": "node scripts/optimize-pngs.js"
  }
}
```

**Asset Optimization Script:**

```javascript
// scripts/optimize-pngs.js
const sharp = require('sharp');
const glob = require('glob');

glob('assets/**/*.png', (err, files) => {
  files.forEach(file => {
    sharp(file)
      .png({ quality: 80, compressionLevel: 9 })
      .toFile(file.replace('assets/', 'dist/assets/'));
  });
});
```

---

## 10. Testing Checklist

- [ ] Global circle renders on all browsers (Chrome, Firefox, Safari, Edge)
- [ ] Timezone highlighting updates every minute
- [ ] Avatar scales smoothly on hover
- [ ] Slot grid responsive on mobile (375px width)
- [ ] Items equip/unequip correctly
- [ ] Canvas renders all layers in correct order
- [ ] Face upload works with various image formats
- [ ] Rarity borders display correctly
- [ ] Keyboard navigation works for all slots
- [ ] Reduced motion preferences respected
- [ ] LocalStorage persists avatar config
- [ ] Assets lazy-load correctly

---

**Document Status:** Complete technical specification  
**Next Steps:** Implement components in order: Global Circle → Studio → Face Upload  
**Last Updated:** March 17, 2026

---

*Designed by Alex | Documented by Cappy*
