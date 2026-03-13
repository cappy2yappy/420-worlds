# 420 Worlds - Game Design Document
**Version:** 1.0  
**Last Updated:** March 12, 2026  
**Target Launch:** April 20, 2026 (PWA MVP)  
**Team:** Laibyrinth (Tony + Alex + Cappy)

---

## Executive Summary

**420 Worlds** is a Roblox-inspired social culture app built around the 4:20 timezone experience. Users create highly customizable avatars, join timezone-based worlds, check in at 4:20, earn weed points, and unlock cosmetic items. The app combines FOMO mechanics (15-minute windows), progression systems (daily streaks, unlockables), and social engagement (chat rooms, region-specific content) to create a sticky, monetizable cannabis culture platform.

**Core Loop:**
1. User's timezone approaches 4:20
2. Countdown creates anticipation (avatar eyes get redder)
3. At 4:20, world opens for 15 minutes
4. User checks in → earns points → chats with community
5. Spends points on drip (outfits, accessories, effects)
6. Returns tomorrow to maintain streak

**Key Differentiator:** We're the only app combining timezone-based celebration events with deep avatar customization and a weed points economy. Competitors (DankSpot, WeedMaps) have no gamification or avatars.

---

## 1. Game Concept

### 1.1 Elevator Pitch
"It's Always 4:20 Somewhere" - A social app where stoners worldwide celebrate 4:20 together, customize their avatars with premium drip, and build daily check-in streaks across multiple timezone worlds.

### 1.2 Target Audience
- **Primary:** 21-35 year old cannabis users in legal states
- **Secondary:** Cannabis culture enthusiasts, collectors, social gamers
- **Demographics:** 60% male, 40% female, urban/suburban, tech-savvy
- **Psychographics:** Social, creative, brand-conscious, routine-oriented

### 1.3 Core Pillars
1. **Community:** Connect with global stoner culture across timezones
2. **Identity:** Express yourself through deep avatar customization
3. **Ritual:** Build daily 4:20 check-in habits and streaks
4. **Collection:** Unlock and showcase rare cosmetics and badges
5. **FOMO:** Limited-time 15-minute windows drive engagement

---

## 2. Core Mechanics

### 2.1 Timezone System
**Concept:** 24 timezones = a new 4:20 event every ~30 minutes, 24/7

**Implementation:**
- Real-time countdown to next 4:20 in user's local timezone
- Animated ring/halo around avatar fills as 4:20 approaches
- Ring color shifts: green (>5 min away) → gold (under 5 min)
- Avatar eyes progressively redden as countdown nears zero

**World Status:**
- 🟢 LIVE: Currently 4:20 in this timezone (join now!)
- ⏳ NEXT: Countdown to next 4:20 (can't join yet)
- User can see all 12 worlds simultaneously on the grid

**Featured Worlds (Phase 1):**
- 🇺🇸 New York
- 🇺🇸 Los Angeles  
- 🇺🇸 Chicago
- 🇺🇸 Denver
- 🇨🇦 Toronto
- 🇬🇧 London
- 🇳🇱 Amsterdam
- 🇩🇪 Berlin
- 🇯🇵 Tokyo
- 🇦🇺 Sydney
- 🇲🇽 Mexico City
- 🇧🇷 São Paulo

### 2.2 Check-In System
**Window:** 15 minutes before 4:20 → 15 minutes after (30-min total)

**Rewards:**
- Base: 420 weed points per check-in
- Streak bonus: +50 points per consecutive day (max +500 at 10 days)
- Region bonus: +100 points for checking in from a new world
- Special events: 2x-5x points on holidays (April 20, 7/10 Dab Day)

**Mechanics:**
- Big green "CHECK IN ✓" button appears when world is live
- Triggers celebration animation (screen flash, confetti, sound)
- Points popup: "+420 💨" with satisfying animation
- Updates streak counter and profile stats

**Streak System:**
- Check in once per day = streak continues
- Miss a day = streak resets to zero
- Streak milestones unlock badges: 🔥7, 🔥30, 🔥100, 🔥365

### 2.3 Avatar System (Deep Customization)

**Philosophy:** Your avatar IS your identity. Gorillaz/chibi anime hybrid style with premium drip culture.

**Customization Layers (MVP):**
1. **Background** (3 options)
   - Wood floor
   - Street/urban
   - Nature/park
   
2. **Body** (6 skin tones)
   - Light
   - Medium-light
   - Medium
   - Medium-dark
   - Dark
   - Very dark

3. **Face** (5 styles)
   - Eyes: round, almond, sleepy, sharp, cat
   - Mouth: smile, smirk, neutral, laughing

4. **Hair** (8 styles × 6 colors = 48 combos)
   - Styles: short, long, afro, dreadlocks, buzz, mohawk, bun, bald
   - Colors: black, brown, blonde, red, purple, green

5. **Clothing - Top** (15 items)
   - T-shirt (8 colors)
   - Hoodie (5 colors)
   - Jacket (leather, denim, varsity)
   - Crop top (3 styles)
   - Tank top (2 styles)

6. **Clothing - Bottom** (10 items)
   - Jeans (blue, black, ripped)
   - Shorts (cargo, athletic)
   - Joggers (3 colors)
   - Skirt (2 styles)

7. **Shoes** (8 items)
   - Sneakers (classic, high-top, designer)
   - Boots (timberland-style, combat)
   - Sandals

8. **Headwear** (10 items)
   - None
   - Baseball cap (forward, backward)
   - Beanie
   - Bucket hat
   - Crown (premium)
   - Bandana

9. **Accessories** (Multi-select, up to 3)
   - Gold chain
   - Diamond chain
   - Sunglasses (aviator, round, pixel)
   - Earrings (studs, hoops)
   - Watch (gold, silver)
   - Blunt/joint (animated)

10. **Effects** (Premium unlockables)
    - Smoke trail
    - Glow aura (color picker)
    - Sparkle effect
    - Floating leaf particles

**Target at Launch:** 200+ unique combinations minimum

**Progression:**
- Free: Basic options in each category (20-30% of items)
- Unlockable: Earn via weed points (60% of items)
- Premium: Drip Pass or direct purchase (10-20% of items)

### 2.4 World Rooms

**Concept:** When you join a live 4:20 world, you enter a room with other users' avatars.

**Visual Style (Phase 1 - MVP):**
- Top-down or isometric view
- 8-12 avatars visible at once
- Each avatar has username label
- Your avatar is highlighted with glow/outline

**Room Features:**
- **Avatars:** Animated idle bobbing, randomized positions
- **Chat:** Scrolling text chat (bottom 1/3 of screen)
- **User count:** "👥 1,247 blazing" 
- **Timer:** "Room closes in: 14:23" (counts down from 15:00)
- **Check-in button:** Large, prominent, one-click

**Chat Moderation (Phase 2):**
- Auto-filter slurs and spam
- Report button
- Temp mute for violations
- Community moderators (volunteer program)

---

## 3. Economy & Progression

### 3.1 Weed Points (💨)

**Earning:**
- Check-in: 420 points (base)
- Daily streak bonus: +50/day (max +500)
- New world bonus: +100 (one-time per world)
- Special events: 2x-5x multipliers
- Achievements: varies (50-500 points)

**Spending:**
- Cosmetics: 420 - 4,200 points
- Effects: 1,260 - 2,520 points
- Rare items: 4,200+ points

**Retention Hook:** Points can't be purchased directly - you MUST check in daily to earn them.

### 3.2 Drip Store

**Item Pricing Tiers:**
- **Common:** 420 points (basic colors, simple items)
- **Uncommon:** 840 points (patterns, unique styles)
- **Rare:** 1,680 points (brand collabs, animated items)
- **Epic:** 2,520 points (effects, special cosmetics)
- **Legendary:** 4,200+ points (ultra-rare, limited edition)

**Featured Items (MVP):**
| Item | Price | Rarity |
|------|-------|--------|
| Gold Chain | 420 | Common |
| Diamond Chain | 840 | Uncommon |
| Cookies Brand Cap | 840 | Uncommon |
| Black Beanie | 420 | Common |
| Crown | 2,100 | Rare |
| Green Hoodie | 630 | Common |
| Leather Jacket | 1,260 | Uncommon |
| Ripped Jeans | 630 | Common |
| Designer Sneakers | 1,050 | Uncommon |
| Blunt Accessory | 420 | Common |
| Sunglasses | 420 | Common |
| Smoke Trail Effect | 1,680 | Rare |
| California Badge | 420 | Common |
| NYC Badge | 420 | Common |
| Amsterdam Badge | 840 | Uncommon |
| Tokyo Badge | 840 | Uncommon |
| VIP Crown | 4,200 | Legendary |
| Glow Aura | 2,520 | Epic |
| Pixel Glasses | 630 | Common |
| Gold Watch | 1,050 | Uncommon |

### 3.3 Badges & Achievements

**Region Badges:**
- Unlock by checking in from that timezone world
- Display on profile
- Collection incentive (gotta catch 'em all)

**Streak Badges:**
- 🔥 7 Day Streak
- 🔥 30 Day Streak
- 🔥 100 Day Streak
- 🔥 365 Day Streak (1 year!)

**Special Achievements:**
- Early Bird: Check in at 4:20 AM
- Night Owl: Check in at 4:20 PM
- World Traveler: Visit all 12 worlds
- Collector: Own 50+ items
- Fashionista: Own 100+ items
- OG: Joined during April 2026 launch month

---

## 4. Monetization

### 4.1 Revenue Streams

**Primary (Launch):**
1. **Avatar Cosmetics** - Direct item purchases ($0.99 - $4.99)
2. **Drip Pass** - Monthly subscription for exclusive items ($4.99/mo or $29.99/yr)

**Secondary (Phase 2):**
3. **Brand Partnerships** - Cookies, Raw, Backwoods create branded items (revenue share)
4. **Affiliate Revenue** - Weedmaps/Leafly dispensary referrals (CPA model)
5. **Advertising** - Cannabis brands target users in legal states (CPM model)

**Tertiary (Phase 3):**
6. **Premium Tier** - Ad-free + bonuses ($4.99/mo)
7. **Limited Drops** - Exclusive seasonal cosmetics (FOMO pricing)
8. **Gifting** - Send items to friends (20% platform fee)

### 4.2 Drip Pass (Subscription)

**Price:** $4.99/month or $29.99/year (save 50%)

**Benefits:**
- 2x weed points on all check-ins
- Access to 20+ exclusive items
- Early access to new cosmetics (1 week before public)
- Exclusive "Drip Pass" badge
- Custom profile themes
- Priority support

**Target:** 5-10% of active users subscribe (industry standard for cosmetic passes)

### 4.3 In-App Purchases

**Cosmetic Packs:**
- Starter Pack: $0.99 (3 items)
- Style Pack: $2.99 (8 items + 500 points)
- Premium Pack: $4.99 (15 items + 1,500 points)
- Legendary Pack: $9.99 (30 items + 4,200 points + exclusive effect)

**Point Boosters (Controversial - TBD):**
- We may avoid selling points directly to preserve check-in engagement
- Alternative: Sell time-limited 2x multipliers ($1.99 for 7 days)

### 4.4 Brand Partnerships

**Target Brands:**
- **Cookies** (clothing line) - Branded caps, hoodies, accessories
- **Raw** (rolling papers) - Joint/blunt accessories, effects
- **Backwoods** - Cigar accessories
- **Leafly** / **Weedmaps** - Affiliate CPA for dispensary visits
- **Local dispensaries** - Geo-targeted offers

**Revenue Model:**
- Brand pays for item creation
- We get 30-50% of item sales
- Brand gets exposure to 18-35 demographic

---

## 5. Technical Specification

### 5.1 Tech Stack (MVP - Phase 1)

**Frontend:**
- HTML5 + CSS3 + Vanilla JavaScript
- Single-file PWA (installable on mobile homescreen)
- Google Fonts: Poppins (body), Rajdhani (headers)
- HTML5 Canvas for avatar rendering

**State Management:**
- localStorage for user data (avatar config, points, inventory)
- Session state in memory (current world, chat messages)

**Backend (Phase 1 - Mock):**
- No real backend for MVP
- Everything runs client-side
- Mock data for world status, chat messages, user counts

**Deployment:**
- Hosted on Hostinger (laibyrinth.com/420/)
- CDN: Hostinger's LiteSpeed Cache
- Domain: Custom domain TBD

### 5.2 Tech Stack (Phase 2 - Production)

**Backend:**
- **Supabase** (Postgres DB + Auth + Realtime)
  - User profiles
  - Inventory/points tracking
  - Real chat messages
  - Leaderboards

**Real-time:**
- Supabase Realtime for live chat
- WebSockets for world status updates

**Auth:**
- Supabase Auth
- OAuth: Google, Apple, Discord
- Age verification: 3rd party API (TBD)

**Assets:**
- **Avatar parts:** 200+ PNG files hosted on CDN
- **3D models (future):** Meshy.ai for generation, Three.js for rendering

**Native Wrapper (Phase 3):**
- React Native for iOS + Android
- Code sharing: 80%+ reuse from web
- Native features: Push notifications, local storage, biometric auth

### 5.3 Data Model (Phase 2)

**Users Table:**
```sql
CREATE TABLE users (
  id UUID PRIMARY KEY,
  username TEXT UNIQUE,
  email TEXT UNIQUE,
  age_verified BOOLEAN,
  created_at TIMESTAMP,
  last_check_in TIMESTAMP,
  streak_count INT,
  total_points INT,
  spent_points INT,
  avatar_config JSONB
);
```

**Inventory Table:**
```sql
CREATE TABLE inventory (
  user_id UUID REFERENCES users(id),
  item_id TEXT,
  acquired_at TIMESTAMP,
  equipped BOOLEAN,
  PRIMARY KEY (user_id, item_id)
);
```

**Check-ins Table:**
```sql
CREATE TABLE check_ins (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  world_id TEXT,
  timestamp TIMESTAMP,
  points_earned INT
);
```

**Chat Messages Table:**
```sql
CREATE TABLE messages (
  id UUID PRIMARY KEY,
  world_id TEXT,
  user_id UUID REFERENCES users(id),
  message TEXT,
  timestamp TIMESTAMP
);
```

---

## 6. Development Roadmap

### Phase 1: MVP (Target: April 20, 2026)

**Week 1-2 (March 11-24):**
- ✅ Age gate with DARE.org redirect
- ✅ Canvas-based avatar system
- ✅ Layered asset rendering (6-9 placeholder assets)
- ✅ Avatar creator UI
- ✅ Main hub with countdown
- ✅ 12 world grid with real-time status

**Week 3 (March 25-31):**
- World rooms with avatars + chat (mock data)
- Check-in system with points
- Drip store (20 items)
- Profile with stats + badges
- localStorage persistence

**Week 4 (April 1-7):**
- Generate real illustrated assets (SeaArt + Higgsfield)
- Replace placeholder graphics
- Mobile optimization
- Bug fixes + polish

**Week 5 (April 8-14):**
- Beta testing with 10-20 users
- Iterate based on feedback
- Performance optimization
- Analytics setup (GA4)

**Week 6 (April 15-19):**
- Final polish
- Marketing assets (screenshots, video)
- Press release draft
- Soft launch prep

**April 20, 2026:**
- **LAUNCH DAY** 🎉
- 5x points event
- Social media push
- PR outreach

### Phase 2: Production Backend (May-June 2026)

**May:**
- Supabase setup + migration
- Real auth system
- Real chat (Supabase Realtime)
- Leaderboards
- Push notifications (web)

**June:**
- Brand partnerships (Cookies outreach)
- Affiliate program (Weedmaps/Leafly)
- Payment integration (Stripe)
- Cosmetics store live
- Drip Pass launch

### Phase 3: Native Apps (July-September 2026)

**July:**
- React Native setup
- iOS build
- Android build
- App Store submission

**August:**
- Native push notifications
- Biometric auth
- Native camera (avatar selfies)
- App Store approval process

**September:**
- App Store launch
- Native marketing push
- Influencer partnerships

### Phase 4: Scale & Expand (Q4 2026)

- 3D avatars (Three.js or Unity)
- Voice chat in rooms
- Creator tools (custom items)
- Esports/competitions
- International expansion

---

## 7. Success Metrics

### 7.1 Launch Targets (April 20 - May 20)

**Acquisition:**
- 1,000 signups in first 24 hours
- 5,000 total users by end of week 1
- 10,000 total users by end of month 1

**Engagement:**
- 40%+ daily active users (DAU/MAU ratio)
- 2.5+ check-ins per user per week
- 5+ minute average session length

**Retention:**
- Day 1: 60%
- Day 7: 40%
- Day 30: 20%

**Monetization (Phase 2):**
- 5% conversion to paid (cosmetics or Drip Pass)
- $2-3 ARPU (average revenue per user)
- $10+ ARPPU (average revenue per paying user)

### 7.2 Year 1 Goals (April 2026 - April 2027)

**Users:**
- 50,000 registered users
- 15,000 monthly active users
- 6,000 daily active users

**Revenue:**
- $25K-50K total revenue
- 2-3 brand partnerships signed
- Drip Pass: 500-750 subscribers

**Engagement:**
- 1M+ total check-ins
- 50K+ chat messages sent
- 10K+ items purchased

---

## 8. Competitive Analysis

### 8.1 Direct Competitors

**DankSpot:**
- Similar "always 420 somewhere" branding
- No avatars, no gamification, basic chat
- Clunky UI, low engagement
- **Our advantage:** Avatar system, progression, FOMO mechanics

**WeedMaps / Leafly:**
- Utility apps (dispensary finders)
- No social features
- **Our advantage:** Community-first, not transactional

**MassRoots (defunct):**
- Failed cannabis social network
- Instagram clone, no differentiation
- **Our advantage:** Unique timezone hook, gamification

### 8.2 Indirect Competitors

**Habbo Hotel / Club Penguin / Gaia Online:**
- Avatar-based social platforms
- Not cannabis-focused
- **Our advantage:** Niche community, 18+ audience, monetization-ready

**Roblox:**
- Deep customization, virtual economy
- Not cannabis-related, younger audience
- **Our advantage:** Adult demographic, cultural relevance, simpler scope

---

## 9. Marketing & Growth

### 9.1 Launch Strategy (April 20, 2026)

**Pre-Launch (April 1-19):**
- Teaser campaign on Instagram/TikTok
- Influencer seeding (10-15 micro-influencers)
- Press outreach (High Times, Leafly, cannabis blogs)
- Email list building (landing page with signup)

**Launch Day (April 20):**
- 5x points event
- Social media blitz
- Press release distribution
- Paid ads (Instagram, Reddit, TikTok)
- Referral program (invite friends, earn bonus points)

**Post-Launch (April 21-30):**
- Daily social content (user showcases, leaderboards)
- Community contests (best avatar, highest streak)
- Gather feedback, iterate fast
- Double down on what works

### 9.2 Growth Channels

**Primary:**
1. **TikTok** - Short clips of avatar customization, 4:20 celebrations
2. **Instagram** - Visual-first platform, avatar showcases
3. **Reddit** - r/trees, r/cannabis, r/gaming crossover

**Secondary:**
4. **Discord** - Community server, support, feedback
5. **Twitter/X** - Real-time updates, memes, engagement
6. **YouTube** - Tutorials, dev vlogs, influencer reviews

**Tertiary:**
7. **Paid ads** - Instagram, Reddit, TikTok (retargeting)
8. **SEO** - Cannabis culture content, app indexing
9. **PR** - Cannabis media, tech blogs, app review sites

### 9.3 Influencer Strategy

**Target:**
- Cannabis lifestyle influencers (10K - 100K followers)
- Gaming/avatar creators
- Cultural commentators

**Offer:**
- Early access + exclusive items
- Affiliate link (10% of referred sales)
- Co-branded cosmetics (your face/brand in the app)

**Goal:** 10-15 influencers promoting by launch

---

## 10. Risks & Mitigations

### 10.1 Technical Risks

**Risk:** PWA performance on older devices  
**Mitigation:** Aggressive optimization, Canvas fallbacks, progressive enhancement

**Risk:** Supabase costs scale too fast  
**Mitigation:** Start with generous free tier, optimize queries, add CDN caching

**Risk:** Asset generation takes too long (200+ items)  
**Mitigation:** Use SeaArt batch generation, start with 50 items and expand

### 10.2 Business Risks

**Risk:** Low user adoption (niche market)  
**Mitigation:** Aggressive marketing, influencer push, viral mechanics (referrals)

**Risk:** Low monetization (users won't pay)  
**Mitigation:** Free-to-play core loop, cosmetics-only monetization (proven model)

**Risk:** App Store rejection (cannabis content)  
**Mitigation:** Position as "lifestyle/culture" app, age gate, no actual sales

### 10.3 Legal Risks

**Risk:** Cannabis advertising restrictions  
**Mitigation:** No actual cannabis sales, age verification, geo-blocking illegal states

**Risk:** Age verification compliance  
**Mitigation:** 3rd party verification API, strict 21+ enforcement

**Risk:** User-generated content moderation  
**Mitigation:** Auto-filters, report system, community moderators

---

## 11. Team & Roles

**Tony (Tech Lead):**
- Frontend development
- System architecture
- Deployment & DevOps

**Alex (Design Lead):**
- Avatar art direction
- UI/UX design
- Brand partnerships

**Cappy (Product/Ops):**
- Research & documentation
- Task coordination
- Asset generation
- QA & testing

**Future Hires (Post-Launch):**
- Backend developer (Supabase)
- 2D artist (cosmetics)
- Community manager
- Marketing/growth lead

---

## 12. Appendix

### 12.1 Reference Links
- Research Brief: `/projects/420-app/research-brief.md`
- Intake Form: `/projects/420-app/intake-form-v2.md`
- Meeting Notes: `/projects/laibyrinth/meeting-notes-feb27-2026.md`
- Live Prototype: https://laibyrinth.com/420/
- GitHub Repo: https://github.com/cappy2yappy/420-worlds

### 12.2 Color Palette
- Primary Background: `#0a0a0a` (deep black)
- Secondary Background: `#1a2e1a` (dark green)
- Accent Green: `#39ff14` (neon green)
- Accent Gold: `#ffd700` (gold)
- Text: `#ffffff` (white)
- Muted Text: `rgba(255,255,255,0.7)`

### 12.3 Typography
- Display: Rajdhani (bold, tech-inspired)
- Body: Poppins (clean, modern)

### 12.4 Key Dates
- Kickoff: March 1, 2026
- MVP Target: April 20, 2026
- Backend Launch: June 1, 2026
- App Store Launch: September 1, 2026

---

**Document Status:** Living document - will be updated as the product evolves.  
**Next Review:** April 21, 2026 (post-launch retrospective)

---

*Built by Laibyrinth | https://laibyrinth.com*
