# Product Spec — "Stacked": True Hourly Rate for the Multi-Gig Generation

**Working name:** Stacked
**Tagline:** *Know your real hourly rate. Across every gig.*
**One-liner:** Stacked aggregates income and hours from every job a person works — gig apps, W-2 shifts, and freelance — into a single, honest, real-time picture of what they're actually earning per hour, after gas, fees, and taxes.

---

## 1. Positioning

Every existing time-clock / time-tracking app assumes one job, one employer. The reality for the target user is 2–4 income streams running at once (e.g. DoorDash + Instacart + a part-time retail shift + occasional freelance work), each with its own app, its own definition of "earnings," and none of them telling the truth about costs (gas, mileage, platform fees, self-employment tax). Nobody owns "what am I actually making, all-in, right now" — that's the blue ocean.

Stacked is not a time clock with more integrations bolted on. It's a **personal income identity app**: the single place a multi-gig worker opens to see their real financial reality, and the single thing they screenshot to prove or vent about it.

**Target user:** 18–34, works 2+ income sources (rideshare/delivery + W-2 shift job + occasional freelance/reselling), financially online (follows loud-budgeting / pay-transparency content), price- and time-sensitive, decides which gig to work today partly on vibes and partly on which app "feels" like it pays better — Stacked replaces the vibes with a number.

---

## 2. Brand & Visual Identity

### 2.1 Name & logo concept
- **Name:** Stacked (app store subtitle: "Real Hourly Rate Tracker")
- **Logomark:** three rounded bars of ascending height, each a different accent color (representing different income streams "stacking" into one total), merging into a single upward arrow negative-space at the top. Reads equally well as a tiny 1-color app icon glyph or a full-color lockup.
- **Icon on device:** solid Ink background, Stack-Green bars, no text — must be legible at 40px.

### 2.2 Color palette

Dark-mode-first (financial-ticker aesthetic reads better on dark, and dark-mode screenshots pop harder on TikTok/IG than light UI chrome). Light mode is a first-class second theme, not an afterthought.

| Role | Name | Hex | Usage |
|---|---|---|---|
| Background (dark) | Ink | `#0B0F0E` | Primary app background, dark mode |
| Background (light) | Cloud | `#F7F7F4` | Primary app background, light mode |
| Surface / card (dark) | Ink Raised | `#161C1A` | Cards, sheets, nav bar on dark |
| Surface / card (light) | Fog | `#EFEFEA` | Cards, sheets on light |
| Primary brand | Stack Green | `#00E28A` | Primary CTA, live ticker, positive numbers, logo |
| Secondary accent | Signal Coral | `#FF5C4D` | Alerts, "you're underpaid" flags, negative deltas |
| Tertiary accent | Sun Yellow | `#FFC93C` | Streaks, badges, celebratory moments |
| Text primary (dark) | Off-White | `#F2F4F2` | Primary text on dark |
| Text primary (light) | Near-Black | `#12140F` | Primary text on light |
| Text muted | Slate | `#8A9490` | Secondary/meta text, both modes |
| Per-platform chips | (native brand tint, e.g. muted versions of each connected gig app's own color) | — | Small icon chips only, never used as app chrome — keeps the aggregation legible without competing with Stack Green |

Numbers that represent money are **always Stack Green when positive/neutral and Signal Coral only when flagging a real problem** (e.g., "this gig pays below minimum wage after gas") — color is a signal, not decoration.

### 2.3 Typography
- **Display / headlines:** Sora (geometric rounded sans, warm but modern) — used for screen titles, big report headlines, and the shareable card text.
- **Body / UI:** Inter — used for labels, lists, settings, secondary text. Highly legible at small sizes, free, ubiquitous.
- **Numerals (all dollar figures, rates, timers):** tabular/monospaced figures — either Inter's tabular-figure variant or a monospace like IBM Plex Mono for the live ticker specifically, so digits don't jitter or reflow as they count up. This is a functional requirement, not just style: a wobbling ticker looks broken on screen recordings.

### 2.4 Style principles
1. **Big numbers, small chrome.** The dollar figure is always the largest element on any screen. Everything else recedes.
2. **Tabular figures always** for anything that updates live or gets compared side-by-side.
3. **Generous rounding** — 20–28px corner radius on cards, pill-shaped buttons and chips. Soft, not sharp; approachable, not corporate-SaaS.
4. **One glow, used sparingly.** The live-earnings ticker gets a subtle Stack Green glow/pulse while active — the single "alive" element on any screen. Nothing else animates constantly, so this reads as special.
5. **Celebration is physical, not just color.** Milestones (streaks, "you hit your rent goal") trigger a brief confetti/particle burst in Stack Green + Sun Yellow — deliberately reminiscent of Duolingo/Cash App "cha-ching" moments, because those moments are what get screen-recorded.
6. **Voice:** direct, plain-spoken, a little wry — never corporate HR-speak. "You made $187 today. After gas, more like $151." Not "Your net adjusted earnings summary is now available."

---

## 3. Core Functionality

### 3.1 MVP feature set

1. **Connect Your Gigs** — link income sources during onboarding:
   - Gig/delivery/rideshare apps (Uber, Lyft, DoorDash, Instacart, Shipt, Amazon Flex, etc.) via bank-linked transaction detection (Plaid) matched against a maintained list of known payout merchant IDs, with manual correction.
   - W-2 / hourly shift jobs via built-in clock-in/clock-out (the baseline time-clock functionality from the original product, retained as one input stream among several).
   - Freelance/cash/tips via quick manual entry.
2. **True Hourly Rate Engine** — for every income stream and blended across all of them, computes **net** hourly rate: gross pay minus mileage (IRS standard mileage rate or user's actual gas spend), minus platform fees, minus a user-set self-employment tax set-aside percentage. This is the core differentiator vs. every competitor, who all report gross.
3. **Live Earnings Ticker** — home-screen and lock-screen widget/Live Activity that counts up in real time while a shift or trip is active, in tabular Stack Green numerals with a soft pulse glow.
4. **Stack Timeline** — one unified feed of every shift/trip across every connected source, color-chipped by platform, replacing the need to check 3–4 separate apps to remember what you worked.
5. **Weekly Stack Report** — an auto-generated, one-tap-shareable recap card (see §4) — total earned across all sources, blended real hourly rate, which gig actually paid best net-of-costs, hours worked, current streak.
6. **Goals & Tax Set-Aside** — a simple "Rent Countdown" / savings-goal bar, plus automatic flagging of how much of this week's earnings should be set aside for taxes.

### 3.2 Phase 2
7. **Community Benchmark** (opt-in, anonymized) — compare your real hourly rate on a given platform, in your city, against the anonymized community average.
8. **Friend Leaderboards** — opt-in comparison/leaderboard of real hourly rate among a friend group, with light gamified streaks and badges.
9. **Gig Recommendation** — "based on the last 4 weeks, Instacart nets you $4.10/hr more than DoorDash in your area right now" — a nudge, not an ad.

---

## 4. What's designed to go viral (organic + paid)

This is the section that differentiates the spec from a generic feature list — every item below exists specifically because it produces shareable, screenshot- or screen-record-native content, modeled on the mechanics that made Spotify Wrapped, Duolingo streaks, and Strava's post-workout cards into organic growth engines.

| Mechanic | Why it spreads |
|---|---|
| **Weekly/monthly Stack Report card** | Auto-generated, pre-formatted for Stories/TikTok/Reels at launch (one tap to share). Personalized + numeric + a little bit of a flex ("I made $612 across 3 gigs this week") — the exact shape of content that already performs on "day in the life of a delivery driver" TikTok. |
| **Live Ticker screen recordings** | The pulsing, counting-up dollar figure is inherently good B-roll — creators already film "watch me hit $200 today" content; Stacked gives them a purpose-built on-screen prop instead of a stopwatch and mental math. |
| **"Real Rate Reveal"** | A single surprising, true statistic surfaced automatically: *"After gas, your $22/hr delivery gig actually pays $14.10/hr."* Shock + honesty is the exact tone of the pay-transparency trend already thriving on TikTok — built to be screenshotted and captioned, and to work as authentic-feeling paid UGC ad creative rather than reading like an ad. |
| **Community Benchmark ("Am I underpaid?")** | Inherently debate-inducing, comment-bait content format; also gives press/creators a recurring, re-shareable local-data hook ("DoorDash drivers in Austin average $14.20/hr net"). |
| **Friend Leaderboard** | Direct K-factor mechanic — invites are required to compare, so sharing is functional, not just promotional. |

Paid social creative should lead with the Real Rate Reveal and the Stack Report card specifically — both are native-feeling, numeric, and personal, which outperforms polished corporate-SaaS ad creative in this demographic.

---

## 5. Primary Screens

### Screen 1 — Home / Today
The default landing screen. Dominated by the **Live Ticker** (large tabular Stack Green numerals, soft pulsing glow) if a shift/trip is active, or "Today's Stack" total if not. Below it, a horizontal row of chips — one per connected gig — each showing today's earnings for that source so far. A single primary CTA: "Clock In" / "Start Trip" (manual sources only; connected gig apps auto-detect). Bottom tab bar: Home, Stack Timeline, Reports, Benchmark, Profile.

### Screen 2 — Stack Timeline
A single reverse-chronological feed merging every shift and trip from every connected source, each entry shown as a compact card: platform chip + icon, time range, gross pay, and net (after mileage/fees) in Stack Green tabular numerals. Filter chips at top to isolate a single platform or view "All Stacked." This screen replaces the need to open 3–4 separate gig apps just to remember what was worked when.

### Screen 3 — Real Rate Breakdown
The core "aha" screen. A ranked list of every connected income source this week, each showing gross $/hr vs. **net $/hr** side by side (net always in Stack Green, with a Signal Coral flag icon if net falls under a user-set "worth it" threshold, e.g. local minimum wage). Tapping a source expands a simple breakdown: gross pay → minus mileage → minus fees → minus tax set-aside → net. Includes a one-tap "Share this breakdown" action that generates the Real Rate Reveal card.

### Screen 4 — Weekly Stack Report (share sheet)
A full-bleed, pre-designed vertical card (Stories/TikTok/Reels aspect ratio) auto-generated every week: total stacked earnings, blended real hourly rate, best-paying gig this week, hours worked, current streak — Sora display type on Ink background with Stack Green numerals and a small Stacked logomark watermark. One tap opens the native share sheet targeted at Instagram Stories / TikTok / Snapchat. This screen IS the growth loop.

### Screen 5 — Benchmark
Shows the user's real hourly rate for a chosen platform plotted against the anonymized community average for their metro area, as a simple horizontal comparison bar (your rate vs. area average), with a one-line honest verdict ("You're earning 18% above the Austin DoorDash average this week"). Includes a share action and an opt-in toggle controlling whether the user's own (anonymized) data contributes to the benchmark.

---

## 6. Data & Integration Approach (feasibility notes)

- **Bank-linked detection (Plaid or equivalent):** classify incoming deposits against a maintained merchant list (Uber, DoorDash, Instacart payout entities, etc.) to auto-populate gross earnings without needing official gig-platform APIs, most of which are not publicly available for this use case.
- **Manual entry / correction:** always available as a fallback and for cash tips, freelance invoices, and W-2 shifts, so the product works fully without bank linking for privacy-conscious users.
- **Mileage:** GPS-based automatic trip mileage (opt-in, background location during active gig hours only) with manual override; net-cost calculation uses IRS standard mileage rate by default, editable to actual fuel cost.
- **Tax set-aside:** simple flat-percentage estimate (user-configurable, defaults based on filing status) — explicitly framed as an estimate, not tax advice.

---

## 7. Monetization

- **Free tier:** unlimited manual tracking, up to 2 connected gig sources, Live Ticker, Stack Timeline, Weekly Stack Report.
- **Stacked Plus (subscription):** unlimited connected sources, Real Rate Breakdown with full fee/mileage/tax detail, Community Benchmark, Friend Leaderboards, tax set-aside automation and export.

---

## 8. Success Metrics

- **North star:** Weekly Stack Reports shared per active user (the organic growth loop, directly instrumentable).
- Supporting metrics: gig sources connected per user (depth of the aggregation value prop), D7/D30 retention, blended CAC on paid social vs. organic-attributed installs, Benchmark opt-in rate (data-flywheel health).
