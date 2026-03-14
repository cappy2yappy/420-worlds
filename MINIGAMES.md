# 420 Worlds - Mini-Games Design Document

**Version:** 1.0  
**Last Updated:** March 14, 2026  
**Status:** In Development (All 5 for April 20 MVP)

---

## Overview

Mini-games are playable **OUTSIDE** the 15-minute 4:20 window to fill time between sessions. They provide:
- Weed points for the economy
- Unlockable items for chat rooms
- Skill-based progression
- Entertainment during countdown periods

**Design Philosophy:** Simple to learn, satisfying to master, rewarding to complete.

---

## 1. Rolling Joints

### Concept
A multi-step crafting game where you prepare joints to bring into chat rooms.

### Gameplay Steps
1. **Take weed out of bag** - Tap/click to grab nugs
2. **Grind weed** - Circular swipe or tap mechanic to fill grinder
3. **Pack joint** - Drag weed into paper, timing-based rolling
4. **Store joints** - Add to inventory

### Success Metrics
- **Speed:** Faster rolling = bonus points
- **Quality:** Perfect timing = "premium joint" (better chat room effects)
- **Quantity:** Roll multiple joints in one session

### Rewards
- 100 weed points per joint rolled
- Joints added to inventory (max 10 at a time)
- Perfect rolls unlock "Master Roller" badge

### Chat Room Integration
- Share joint with room = animated smoke effect on all avatars
- Other players can "puff puff pass" (social emote chain)
- Rare joints (gold paper, flavored wraps) = premium items

### UI/UX
- Top-down view of rolling tray
- Drag-and-drop mechanics
- Visual feedback (weed fills grinder, paper wraps tightly)
- Satisfying animations (spark the joint at the end)

### Technical Notes
- HTML5 Canvas or SVG for drag interactions
- localStorage to save joint inventory
- Particle effects for smoke in chat room

---

## 2. Hotboxing Car

### Concept
Tap rapidly to fill a car interior with smoke, earn a visual buff for your avatar.

### Gameplay
1. **Car interior view** - Dashboard, windshield, seats visible
2. **Tap mechanic** - Button looks like a lighter, tap to "light up"
3. **Smoke fills interior** - Opacity increases with each tap
4. **Success threshold** - Hit 100% smoke = hotbox complete

### Success Metrics
- **Taps per second** - Faster = quicker completion
- **Smoke density** - Visual meter shows progress (0-100%)
- **Time limit** - 60 seconds to max out (or fail)

### Rewards
- 250 weed points on completion
- "Reek" buff: Avatar has smoke particles for 30 minutes
- Unlocks "Hotboxer" badge

### Buff Details: "Reek"
- **Visual:** Smoke trails/particles around avatar in chat rooms
- **Duration:** 30 minutes real-time
- **Social:** Other players can see the effect (flex)
- **Stacking:** Can't stack multiple buffs (30-min cooldown)

### Driving Mechanic (Phase 2 - Future)
- After hotboxing, drive car to chat room location
- Simple top-down driving (arrow keys or tilt controls)
- Arrive at location = bonus points

### UI/UX
- Car interior illustrated background
- Big center button (lighter graphic)
- Smoke animation overlays window
- Sound effects: lighter flick, inhale/exhale

### Technical Notes
- Tap counter with throttle (prevent cheating)
- CSS opacity animations for smoke
- Timer with visual countdown

---

## 3. Coppin' Weed

### Concept
Two-part mini-game: call the weed man, then dap him up when he arrives.

### Part 1: Calling the Weed Man
**Mechanic:** Rapid number dialing in intervals

**Gameplay:**
1. Phone screen appears with number pad
2. Sequence of numbers flash briefly (e.g., "555-0420")
3. You must dial the number FAST in correct order
4. Each digit correct = progress bar fills
5. Complete sequence = call connected

**Difficulty:**
- Easy: 4-digit number, 10 seconds
- Medium: 7-digit number, 8 seconds
- Hard: 10-digit number, 5 seconds

### Part 2: Dap Him Up (Timing Game)
**Mechanic:** Rhythm/timing challenge (Guitar Hero style)

**Gameplay:**
1. Weed man appears on screen
2. Circles shrink toward center (like osu! or Friday Night Funkin')
3. Tap when circle aligns perfectly = successful dap
4. 3 successful daps in a row = transaction complete

**Fail States:**
- Miss the dap = lose points, can retry
- Take too long = weed man leaves, game over

### Rewards
- 200 weed points on success
- Weed added to inventory (used for rolling joints)
- Rare items: "Designer Weed" (gold nugs) = 2x rolling speed

### UI/UX
- Phone UI for dialing (realistic iOS/Android style)
- Character animations for dap sequence
- Street corner background (urban vibe)

### Technical Notes
- Input sequence validation
- Timing hitboxes (generous for casual, tight for perfect)
- Cooldown timer (can't spam the game)

---

## 4. Hiding Weed from Cops

### Concept
Stealth/timing game where you throw weed out the car window when cops aren't looking.

### Gameplay
1. **Setup:** You get pulled over (random event trigger)
2. **Cop position:** Officer walks around car, looking in windows
3. **Distraction windows:** 2 moments where cop is distracted (looks away, talks on radio)
4. **Your action:** Tap to throw weed out the window during distraction
5. **Success:** Cop doesn't notice = you're clear

### Distraction Events
1. **Cop looks at phone** - 2-second window
2. **Another car drives by** - 3-second window

### Fail States
- Throw when cop is watching = busted (lose weed + points)
- Don't throw in time = cop searches car, finds weed (bigger penalty)

### Success Outcomes
- **Perfect (both distractions used):** Keep weed + 300 bonus points + "Smooth Criminal" badge
- **Good (threw during 1 distraction):** Keep weed, no bonus
- **Fail:** Lose weed, lose 500 points, 10-min cooldown

### UI/UX
- Side-view of car + cop character
- Visual cues for distractions (phone lights up, car passes by)
- Tension-building music
- Quick-time button prompt (THROW!)

### Technical Notes
- Randomized distraction timing (not memorizable)
- Animation states for cop (walking, looking, distracted)
- Sound cues (radio chatter, car engine)

---

## 5. Cleaning Game

### Concept
Maintenance mini-game where you clean smoking accessories for bonuses.

### Three Cleaning Tasks

#### 5.1 Scrub Bong
**Mechanic:** Swipe/tap to scrub dirty spots

**Gameplay:**
1. Bong appears with brown resin spots (5-10 spots)
2. Swipe over each spot to clean (progress bar per spot)
3. Clean all spots = sparkling bong

**Reward:** 50 points, bong item unlocked for profile display

#### 5.2 Dust Out Grinder
**Mechanic:** Shake or rapid-tap to knock out kief

**Gameplay:**
1. Grinder screen shows clogged holes
2. Tap rapidly or shake device (mobile) to dislodge particles
3. Meter fills as kief collects in bottom chamber

**Reward:** 50 points + bonus kief (used for premium joint rolling)

#### 5.3 Clean Bowl
**Mechanic:** Tap to knock out ash, swipe to wipe clean

**Gameplay:**
1. Bowl piece shows black ash buildup
2. Tap to knock ash into tray (satisfying animation)
3. Swipe with pipe cleaner to scrub inside
4. Rinse with virtual water (optional)

**Reward:** 50 points, clean bowl = 10% faster rolling joints

### Item Degradation System
- Items don't degrade automatically (no forced maintenance)
- Cleaning is OPTIONAL but gives bonuses:
  - Clean bong = chat room decoration
  - Clean grinder = faster weed processing
  - Clean bowl = aesthetic flex

### UI/UX
- Close-up view of each item
- Dirt particles that disappear when cleaned
- Before/after comparison screen
- Satisfying sparkle effect when done

### Technical Notes
- Swipe detection (mouse drag or touch)
- Progress tracking per spot/area
- Item state saved in localStorage

---

## Mini-Game Economy

### Points Breakdown
| Mini-Game | Base Points | Perfect Bonus | Time to Complete |
|-----------|-------------|---------------|------------------|
| Rolling Joints | 100/joint | +50 (perfect roll) | 30-60 sec |
| Hotboxing Car | 250 | +100 (under 30 sec) | 30-60 sec |
| Coppin' Weed | 200 | +100 (perfect daps) | 45-90 sec |
| Hiding from Cops | 0 (defensive) | +300 (perfect hide) | 20-40 sec |
| Cleaning (all 3) | 150 total | +50 (all perfect) | 2-3 min |

### Cooldowns (Prevent Grinding)
- Rolling Joints: None (unlimited)
- Hotboxing Car: 30 minutes
- Coppin' Weed: 1 hour
- Hiding from Cops: Random event only
- Cleaning: 24 hours per item

### Daily Challenges (Phase 2)
- "Roll 10 joints in 5 minutes"
- "Hotbox without missing a tap"
- "Call the weed man in under 3 seconds"
- Completion = 2x points for the day

---

## Item Drops & Unlockables

### Items Earned from Mini-Games

**Rolling Joints:**
- Basic joint (common)
- Gold paper joint (rare, 5% drop)
- Flavored wraps (uncommon, 15% drop)

**Hotboxing Car:**
- Smoke trail effect (permanent unlock)
- Car decoration for profile (rare)

**Coppin' Weed:**
- Designer weed (gold nugs, 10% faster rolls)
- Weed man contact card (profile badge)

**Hiding from Cops:**
- "Smooth Criminal" badge
- Stealth shades (sunglasses cosmetic)

**Cleaning:**
- Sparkling bong (profile decoration)
- Kief collector (2x kief per grind)
- Pipe cleaner accessory (avatar item)

### Item Usage in Chat Rooms
- Joints: Share with room (group smoke animation)
- Bong: Display as room decoration (if you're VIP)
- Accessories: Equip on avatar for social flex

---

## Progression & Mastery

### Skill Levels (Per Mini-Game)
Track player progress with XP:
- Novice (0-100 XP)
- Apprentice (100-500 XP)
- Skilled (500-1500 XP)
- Expert (1500-5000 XP)
- Master (5000+ XP)

### Unlocks by Level
- **Novice:** Basic items only
- **Apprentice:** Uncommon items (15% drop)
- **Skilled:** Rare items (5% drop), custom animations
- **Expert:** Legendary items (1% drop), leaderboard access
- **Master:** Exclusive badge, profile frame, title

### Leaderboards
- Fastest joint roller
- Most taps in hotbox game
- Perfect dap streak
- Cleanest setup

---

## Technical Architecture

### Data Model
```javascript
{
  miniGames: {
    rollingJoints: {
      gamesPlayed: 0,
      jointsRolled: 0,
      perfectRolls: 0,
      xp: 0,
      level: 1
    },
    hotboxing: {
      gamesPlayed: 0,
      completions: 0,
      fastestTime: null,
      xp: 0,
      level: 1,
      lastPlayed: timestamp
    },
    coppinWeed: {
      gamesPlayed: 0,
      successRate: 0.0,
      perfectDaps: 0,
      xp: 0,
      level: 1,
      lastPlayed: timestamp
    },
    hidingFromCops: {
      encounters: 0,
      successes: 0,
      perfectHides: 0,
      xp: 0,
      level: 1
    },
    cleaning: {
      itemsCleaned: 0,
      lastCleaned: {
        bong: null,
        grinder: null,
        bowl: null
      },
      xp: 0,
      level: 1
    }
  },
  inventory: {
    joints: [],
    weed: 0,
    kief: 0,
    items: [],
    buffs: []
  }
}
```

### File Structure
```
prototype/
  minigames/
    rolling-joints.html
    hotboxing.html
    coppin-weed.html
    hiding-cops.html
    cleaning.html
  assets/
    minigames/
      bong.png
      grinder.png
      joint.png
      car-interior.png
      cop.png
      phone-ui.png
```

### Integration with Main App
- Mini-game buttons appear on main hub during countdown
- "Play while you wait" CTA
- Earned items sync to main inventory
- Points update in real-time

---

## Art Requirements

### Illustrations Needed
- Car interior (dashboard, windshield, seats)
- Cop character (3 poses: walking, looking, distracted)
- Phone UI mockup
- Bong, grinder, bowl (dirty + clean versions)
- Rolling tray + weed + papers
- Street corner background
- Weed man character

### Animations
- Smoke filling car (opacity fade-in)
- Joint rolling (paper wraps around weed)
- Dap sequence (hands meeting)
- Cleaning (dirt particles disappearing)

### Sound Effects (Phase 2)
- Lighter flick
- Inhale/exhale
- Phone dial tones
- Dap sound (slap)
- Cop radio chatter
- Scrubbing/cleaning sounds

---

## Development Roadmap

### Week 1 (March 14-21): Core Mechanics
- Rolling joints prototype (Canvas-based dragging)
- Hotboxing tap mechanic
- Points integration with main economy

### Week 2 (March 22-28): Advanced Games
- Coppin' weed (phone + dap mechanics)
- Hiding from cops (timing + stealth)
- Cleaning game (swipe detection)

### Week 3 (March 29-April 4): Polish & Integration
- Art assets for all games
- Inventory system
- Item usage in chat rooms

### Week 4 (April 5-11): Testing & Balance
- Cooldown tuning
- Point economy balancing
- Bug fixes

### Week 5 (April 12-19): Final Polish
- Sound effects
- Animations
- Leaderboards
- Achievement system

### April 20: Launch
- All 5 mini-games live and functional

---

## Success Metrics

### Engagement Goals
- 60%+ of users play at least one mini-game daily
- Average 3-5 mini-game sessions per user per day
- 20%+ of users reach "Skilled" level in at least one game

### Retention Impact
- Mini-games reduce churn during countdown periods
- Target: 10% increase in Day 7 retention vs. no mini-games

### Monetization
- Premium items unlocked via mini-game mastery
- "Skip cooldown" IAP (controversial, TBD)
- Cosmetic rewards drive Drip Store purchases

---

**Document Status:** Living document - will update as mechanics are refined.  
**Next Review:** Weekly during development sprint

---

*Built by Laibyrinth | https://laibyrinth.com*
