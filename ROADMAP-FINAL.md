# 420 Worlds - FINAL Development Roadmap
**Updated:** March 16, 2026 (Based on Alex's Complete Questionnaire)  
**Launch Target:** April 27, 2026 (REVISED - was April 20)  
**Days Remaining:** 42 days  
**Status:** ALL FEATURES CONFIRMED - Full build-out required

---

## Executive Summary

**Alex's Decision:** Ship ALL 5 mini-games + full feature set for MVP. Delay launch to April 27 if needed.

**Reason for Delay:** Original April 20 target impossible with expanded scope (4x increase).  
**New Target:** April 27 (still within 4/20 week, maintains cultural relevance)

---

## Confirmed Scope Changes from Alex

### Mini-Games (All 5 Required)
1. **Cleaning Game** ⭐ HIGHEST PRIORITY
2. Rolling Joints (TWO modes: timed + no-pressure)
3. Hotboxing Car (100 taps, 1-hour buff)
4. Coppin' Weed (4-stage: pedal → jump → dap → memory)
5. Hiding from Cops (triggered by fail OR standalone)

### Inventory & Trading
- WoW-style loot system (Common → Legendary)
- Unlimited storage, equip up to 3 items
- Full trading between players
- Item degradation (10-hour timer)

### Chat Rooms
- Multiple rooms per timezone (load-balanced, 32 players each)
- Random backgrounds from timezone pool
- Players can switch rooms during session
- Chat history resets after each 4:20

### Backgrounds
- **Start with 36** (3 per timezone) per Alex answer "1"
- Art style: Streets of Rage meets Gorillaz + Japanese anime
- Static images for MVP

### Character Creator
- 3 genders with body type variations
- Priority: Head shape > Eyes > Mouth > Nose
- 6 skin tones (current is fine)

---

## Revised Timeline (42 Days to Launch)

### Week 1: March 16-22 (FOUNDATION)

**Priority 1: Cleaning Game (Alex's #1)**
- Bong scrubbing mechanic (tap/swipe)
- Grinder dusting mechanic
- Bowl cleaning mechanic
- 10-hour degradation timer
- Item unlocks (bongs, grinders, bowls)
- WoW-style rarity tiers

**Estimated Time:** 25-30 hours  
**Owner:** Cappy builds prototype, Codex/Claude Code refines  
**Assets Needed:** Bong, grinder, bowl (dirty + clean = 6 PNGs)

**Priority 2: Inventory System**
- Unlimited storage UI
- Equipment slots (3 max equipped)
- Item categories (consumables vs. permanent)
- Rarity tier visual system (color-coded borders)

**Estimated Time:** 15-20 hours  
**Owner:** Cappy

**Deliverable by March 22:**
- Working Cleaning Game
- Inventory UI with equipment slots
- Item degradation system live

---

### Week 2: March 23-29 (ROLLING JOINTS + HOTBOX)

**Mini-Game 2: Rolling Joints**
- TWO modes: Timed Challenge + No Pressure
- 4-step process (bag → grind → pack → store)
- Max 5 joints for chat room
- Perfect timing mechanic

**Estimated Time:** 18-22 hours  
**Assets Needed:** Rolling tray, weed, grinder, papers (8-10 PNGs)

**Mini-Game 3: Hotboxing Car**
- Car interior background
- 100-tap mechanic
- Smoke fill animation (opacity)
- 1-hour "Reek" buff system

**Estimated Time:** 12-15 hours  
**Assets Needed:** Car interior, smoke overlay, lighter icon (4-6 PNGs)

**Chat Room Sharing**
- Share joint button
- Smoke particles on all avatars
- Red eye effect (progressive)
- Buff system integration

**Estimated Time:** 10-12 hours

**Deliverable by March 29:**
- Rolling Joints (both modes) functional
- Hotbox game functional
- Sharing mechanics in chat rooms
- Buff visual effects working

---

### Week 3: March 30-April 5 (COPPIN' + HIDING + TRADING)

**Mini-Game 4: Coppin' Weed (4-Stage Game)**
- Stage 1: Pedal bike to corner (tap mechanic)
- Stage 2: Time jump off bike
- Stage 3: Dap up seller (rhythm game)
- Stage 4: Memory game (phone number)

**Estimated Time:** 20-25 hours (most complex mini-game)  
**Assets Needed:** Bike, corner background, weed man character, phone UI (10-12 PNGs)

**Mini-Game 5: Hiding from Cops**
- Cop character (3 poses)
- 2 random distraction windows
- Throw weed mechanic
- Snack item reward

**Estimated Time:** 15-18 hours  
**Assets Needed:** Cop character (3 poses), car side-view (5-7 PNGs)

**Trading System**
- Trade UI (drag-and-drop)
- Confirm/cancel flow
- Trade log/history

**Estimated Time:** 12-15 hours

**Deliverable by April 5:**
- All 5 mini-games functional
- Trading system live
- Full gameplay loop working (cop → roll → share → trade)

---

### Week 4: April 6-12 (CHAT ROOMS + BACKGROUNDS)

**Chat Room System**
- Load balancing (auto-assign to room with <32 players)
- Room switching UI
- Random background per room (from timezone pool)
- Chat reset after 4:20 session

**Estimated Time:** 25-30 hours

**Backgrounds (36 Total - 3 per Timezone)**
- Streets of Rage x Gorillaz x Japanese anime style
- 12 timezones × 3 backgrounds = 36 total
- Static images, optimized for web

**Estimated Time:** 30-40 hours (generation + optimization)  
**Owner:** Cappy (SeaArt batch generation)

**Check-In System**
- Big green button at 4:20
- Points calculation (base + streak + bonuses)
- Celebration animation

**Estimated Time:** 8-10 hours

**Deliverable by April 12:**
- Chat rooms with load balancing
- 36 backgrounds integrated
- Check-in system functional

---

### Week 5: April 13-19 (LEADERBOARDS + POLISH)

**Leaderboards (Alex: "All of them")**
- Total weed points
- Longest streak
- Most joints rolled
- Mini-game high scores (per game)
- Items collected
- Trades completed

**Estimated Time:** 15-20 hours

**Social Features**
- View other players' stats
- Emotes (item-based)
- Gifting UI

**Estimated Time:** 12-15 hours

**UI/UX Polish**
- Smooth transitions
- Loading states
- Error handling
- Mobile optimization (tap targets, responsive)

**Estimated Time:** 20-25 hours

**Sound Effects + Music (Alex: YES)**
- Lighter flick, inhale/exhale, scrubbing, tapping
- Background music (chill beats)
- Sound toggle

**Estimated Time:** 15-20 hours (sourcing + integration)

**Deliverable by April 19:**
- Leaderboards live
- Social features working
- Sound effects integrated
- UI polished

---

### Week 6: April 20-26 (TESTING + FINAL PUSH)

**Beta Testing**
- 20-30 beta testers
- Feedback loop
- Bug triage (critical vs. nice-to-have)

**Estimated Time:** 20-25 hours

**Bug Fixing**
- Cross-browser testing
- Mobile device testing
- Edge cases (timezone bugs, inventory overflow, etc.)

**Estimated Time:** 25-30 hours

**Performance Optimization**
- Asset compression
- Canvas rendering optimization
- localStorage management
- CDN caching

**Estimated Time:** 10-15 hours

**Marketing Assets**
- Screenshots
- Gameplay video clips
- Press release
- Social media content

**Estimated Time:** 10-12 hours

**Deliverable by April 26:**
- Bug-free MVP
- All features tested
- Marketing ready

---

### April 27: LAUNCH DAY 🎉

**12:00 AM ET:** Go live  
**All day:** 5x points event  
**Social media:** Coordinated push  
**Monitoring:** Real-time bug fixes

---

## Asset Generation Schedule

### Total Assets Needed: ~280-320

**Week 1 (Cleaning Game):**
- Bong, grinder, bowl (dirty + clean) = 6 assets

**Week 2 (Rolling + Hotbox):**
- Rolling: 10 assets
- Hotbox: 6 assets
- **Subtotal:** 16 assets

**Week 3 (Coppin' + Hiding):**
- Coppin': 12 assets
- Hiding: 7 assets
- **Subtotal:** 19 assets

**Week 4 (Backgrounds):**
- 36 backgrounds (3 per timezone × 12)

**Week 5 (Character Assets):**
- 120 facial features (10 eyes, 10 noses, 10 mouths, 10 head shapes × 3 genders)
- Clothing: 50+ items

**Grand Total:** ~250-300 assets

**Generation Rate Needed:** 6-7 assets per day (42 days)

---

## Team Allocation

**Cappy:**
- Asset generation (SeaArt + Higgsfield)
- Cleaning Game prototype
- Inventory system
- Testing + QA

**Tony:**
- Chat room system
- Trading system
- Deployment
- Performance optimization

**Codex/Claude Code:**
- Coppin' Weed (most complex)
- Leaderboards
- Code refactoring

**Alex:**
- Art direction
- Design feedback
- Marketing assets
- Beta testing coordination

---

## Risk Mitigation

### 🔴 HIGH RISK

**1. Asset Generation Bottleneck**
- **Risk:** 250+ assets in 42 days = 6/day consistently
- **Mitigation:** Batch generation, templates, reuse base layers
- **Backup:** Reduce facial options to 6 per feature (saves 48 assets)

**2. Coppin' Weed Complexity**
- **Risk:** 4-stage mini-game = most code + most assets
- **Mitigation:** Build in isolation, test each stage separately
- **Backup:** Simplify to 2 stages (pedal + dap, cut memory game)

**3. Timeline Pressure**
- **Risk:** 42 days for massive scope
- **Mitigation:** Daily standups, ruthless prioritization
- **Backup:** Delay to May 4 (still within 4/20 month)

### 🟡 MEDIUM RISK

**4. Trading System Exploits**
- **Risk:** Players trade duped items, economy breaks
- **Mitigation:** Server-side validation (Phase 2 with Supabase)
- **Backup:** Disable trading for MVP, add post-launch

**5. Item Degradation Annoyance**
- **Risk:** 10-hour cleaning requirement frustrates casual players
- **Mitigation:** Make degradation optional (dirty items = lower stats, not broken)
- **Backup:** Extend to 24 hours, add "auto-clean" premium item

### 🟢 LOW RISK

**6. Sound Effects**
- **Risk:** Licensing issues, time-consuming
- **Mitigation:** Use royalty-free libraries (Freesound, Zapsplat)
- **Backup:** Launch without sound, add in v1.1

---

## Success Criteria

### Must-Have (Launch Blockers)
- ✅ All 5 mini-games functional
- ✅ Inventory + trading system
- ✅ Chat rooms with load balancing
- ✅ 36 backgrounds
- ✅ Item degradation + cleaning loop
- ✅ Leaderboards

### Nice-to-Have (Post-Launch OK)
- Sound effects (can add in v1.1)
- Advanced social features (friend lists, DMs)
- Real-time chat (can use mock for MVP)
- 3D avatars

### Launch Metrics
- 1,000 signups in first 48 hours
- 60%+ of users play at least one mini-game
- 40%+ of users trade items within first week
- No critical bugs

---

## Daily Standup Format

**Every day at 2:00 PM ET (Discord thread):**

1. What shipped yesterday?
2. What's shipping today?
3. Blockers?
4. Asset needs?

**Participants:** Tony, Alex, Cappy  
**Duration:** 5-10 minutes  
**Format:** Async (post updates in thread)

---

## Go/No-Go Decision Points

### March 22 (End of Week 1)
**Question:** Is Cleaning Game functional with item system?  
**Go:** Proceed to Rolling + Hotbox  
**No-Go:** Extend Week 1 by 3 days, delay launch to May 4

### March 29 (End of Week 2)
**Question:** Are Rolling + Hotbox + Sharing mechanics working?  
**Go:** Proceed to Coppin' + Hiding  
**No-Go:** Cut Coppin' to 2 stages (pedal + dap only)

### April 5 (End of Week 3)
**Question:** Are all 5 mini-games playable?  
**Go:** Proceed to chat rooms + backgrounds  
**No-Go:** Delay launch to May 4

### April 12 (End of Week 4)
**Question:** Are chat rooms + 36 backgrounds + check-in live?  
**Go:** Proceed to polish + testing  
**No-Go:** Reduce backgrounds to 24 (2 per timezone)

### April 19 (End of Week 5)
**Question:** Is the app bug-free and ready?  
**Go:** Launch April 27  
**No-Go:** Launch May 4 (1-week buffer)

---

## Post-Launch Roadmap (April 28 - May 31)

### Week 1 Post-Launch (April 28 - May 4)
- Monitor analytics (GA4)
- Fix critical bugs in real-time
- Gather user feedback
- Iterate on pain points

### Week 2-4 (May 5-25)
- Add sound effects (if not in MVP)
- Polish mini-game animations
- Expand backgrounds (24 → 60)
- Friend lists + DMs

### Phase 2 (June - July)
- Supabase backend (real chat, auth)
- Server-side trading validation
- Push notifications (web)
- Mobile app (React Native)

---

## Commitment

**Launch Date:** April 27, 2026 (FINAL)  
**Status:** COMMITTED - All features confirmed by Alex  
**Backup Date:** May 4, 2026 (if critical blockers)

**Tony:** "I'll handle chat rooms, trading, deployment."  
**Alex:** "I'll provide art direction and marketing assets."  
**Cappy:** "I'll generate all assets, build Cleaning Game, and coordinate everything."

---

*Roadmap last updated: March 16, 2026 4:55 AM ET*  
*Next review: March 22, 2026 (end of Week 1)*
