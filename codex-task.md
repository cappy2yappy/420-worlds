# 420 Worlds - Build Task for Codex

## Current State
- Basic HTML5 web app at /Users/cappy/.openclaw/workspace/projects/420-app/prototype/index.html
- Navigation works
- Avatars are too basic (just CSS shapes - circles and rectangles)
- Need to upgrade to illustrated, layered character system

## Requirements from Alex (Product Owner)

### 1. Age Gate Fix
- ✅ YES button: should make the age gate disappear completely
- ✅ NO button: redirect to https://dare.org (charity partner placeholder)

### 2. Avatar System Upgrade
Reference the illustrated card style in Alex's screenshots (need to generate similar quality)

**Layers needed:**
- Background (customizable)
- Body base (different skin tones)
- Hair (customizable styles + colors)
- Clothing (tops, bottoms)
- Accessories (hats, chains, glasses, etc.)

### 3. Asset Generation Strategy
Use SeaArt AI (already logged in at seaart.ai) + Higgsfield for upscaling:
- Generate 2-3 variations per category as proof of concept
- Save assets to /Users/cappy/.openclaw/workspace/projects/420-app/prototype/assets/

### 4. Tech Approach
- HTML5 Canvas for layering system
- Layer PNGs on top of each other based on user selection
- Similar to Picrew / Gaia Online / Neopets avatar creators

## What to Build

1. **Fix age gate** (YES disappears, NO redirects to DARE.org)
2. **Generate 2-3 asset sets** via SeaArt (bodies, hair, tops minimum)
3. **Build Canvas layering system** that composites the assets
4. **Update avatar creator UI** to show the layered result
5. **Prove customization works** - user can swap parts and see changes

## Constraints
- Single HTML file preferred (keep it simple)
- Must work on mobile + desktop
- Dark theme (blacks, dark greens, neon green #39ff14, gold #ffd700)
- Store selections in localStorage

## Deliverables
- Updated index.html with working layered avatar system
- At least 6-9 PNG assets in /assets/ folder
- Git commit when done
- FTP upload to laibyrinth.com/420/

## Context
This is for an April 20, 2026 launch. Basic prototype exists but needs visual upgrade to match the illustrated style Alex is envisioning (Gorillaz/chibi hybrid aesthetic).

Build it.
