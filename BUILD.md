# 420 Worlds - Build Instructions for Codex

## Current Status
✅ Basic web app working (age gate, navigation, countdown, worlds grid, chat, store)  
❌ Avatars are too basic (CSS circles/rectangles - needs illustrated art)  
❌ Age gate doesn't disappear properly on YES  
❌ NO button doesn't redirect to DARE.org  

## What Needs to Be Built

### Priority 1: Fix Age Gate (Quick Win)
**File:** `index.html`

**Current behavior:**
- YES button calls `verifyAge(true)` but age gate screen stays visible
- NO button does nothing

**Required behavior:**
- YES: Age gate disappears completely, show avatar creator
- NO: Redirect browser to https://dare.org

**Code location:** Search for `function verifyAge(isOver21)` around line 1093

### Priority 2: Avatar System Upgrade (Main Task)

**Current state:** 
Avatars are drawn with basic CSS:
```html
<div class="avatar-body" style="background: #ffdbac"></div>
<div class="avatar-hair" style="background: #333"></div>
<div class="avatar-top" style="background: #39ff14"></div>
```

**Target state:**
Layered PNG system like Picrew/Gaia Online:
```
Canvas layers (bottom to top):
1. Background PNG
2. Body PNG (skin tone)
3. Hair PNG (style + color)
4. Clothing PNG
5. Accessories PNG
```

**Implementation approach:**

1. **Create asset structure:**
```
prototype/
  assets/
    backgrounds/
      bg1.png
      bg2.png
    bodies/
      light.png
      medium.png
      dark.png
    hair/
      short-black.png
      long-blonde.png
      afro-brown.png
    tops/
      tshirt-green.png
      hoodie-black.png
      jacket-red.png
    accessories/
      chain.png
      glasses.png
      cap.png
```

2. **For now: Use placeholder assets**
Since we can't generate real illustrated art yet, create simple colored SVGs or use emoji-based placeholders that demonstrate the layering works. The visual upgrade can come later.

3. **Build Canvas compositor:**
```javascript
function renderAvatar(canvasId, config) {
  const canvas = document.getElementById(canvasId);
  const ctx = canvas.getContext('2d');
  
  // Clear canvas
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  
  // Load and layer images
  const layers = [
    config.background,
    config.body,
    config.hair,
    config.top,
    config.accessories
  ];
  
  // Draw each layer in order
  layers.forEach(imgPath => {
    if (imgPath) {
      const img = new Image();
      img.src = imgPath;
      img.onload = () => ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
    }
  });
}
```

4. **Update avatar creator UI:**
Replace the current `<div class="avatar-display">` with `<canvas id="avatarCanvas" width="400" height="400"></canvas>`

5. **Wire up selections:**
When user clicks a color button, update the config object and re-render:
```javascript
function setSkin(tone) {
  state.avatar.body = `assets/bodies/${tone}.png`;
  renderAvatar('avatarCanvas', state.avatar);
  saveState();
}
```

### Priority 3: Background Customization (Alex's Requirement)
Add a new customization section in the avatar creator:
```html
<div class="custom-section">
  <h3>Background</h3>
  <div class="style-options">
    <div class="style-btn" onclick="setBackground('wood')">Wood Floor</div>
    <div class="style-btn" onclick="setBackground('street')">Street</div>
    <div class="style-btn" onclick="setBackground('nature')">Nature</div>
  </div>
</div>
```

## Technical Constraints

- **Single HTML file:** Keep everything in `index.html` (inline CSS/JS)
- **Mobile-first:** Must work on 375px width
- **localStorage:** Persist avatar config across sessions
- **Color scheme:** Dark greens (#1a2e1a), neon green (#39ff14), gold (#ffd700)

## Testing Checklist

After building, verify:
- [ ] Age gate: YES makes it disappear
- [ ] Age gate: NO redirects to dare.org
- [ ] Avatar creator shows Canvas instead of CSS shapes
- [ ] Clicking customization options updates the Canvas
- [ ] Avatar appears correctly in main hub
- [ ] Avatar appears correctly in profile
- [ ] Changes persist after page reload (localStorage)

## Deployment

After building:
```bash
git add -A
git commit -m "Upgrade avatar system to Canvas-based layering"
git push

# Upload to live site
python3 << 'EOF'
import ftplib
ftp = ftplib.FTP('82.29.157.91')
ftp.login('u594702311.laibyrinth.com', 'Casio#419')
ftp.cwd('/public_html/420')
with open('index.html', 'rb') as f:
    ftp.storbinary('STOR index.html', f)
ftp.quit()
print("✓ Uploaded to https://laibyrinth.com/420/")
EOF
```

## Success Criteria

**Minimum viable:**
1. Age gate works correctly (YES disappears, NO redirects)
2. Avatar creator uses Canvas with at least 3 placeholder assets per category
3. User can customize and see changes in real-time
4. Changes persist in localStorage

**Stretch goal:**
1. Generate 2-3 illustrated assets via SeaArt to replace placeholders
2. Add smooth transitions between customization changes
3. Export avatar as downloadable PNG

## Notes

- Don't worry about perfect art yet - prove the system works first
- Alex will provide design references later for real asset generation
- April 20, 2026 deadline - focus on functionality over polish
- This is a proof-of-concept to show investors/partners

Build it.
