# Game360 onboarding — Growth, Operations & Product Design

**For:** Nonye  
**Focus:** Growth & operations + product design support  
**Primary tool:** Control Tower (admin dashboard)  
**Companion:** Growth OS (inside Control Tower → Growth OS)

Welcome. This guide is the walkthrough doc for your first days on Game360: what the product is, how money and players work, and how to operate every major module in Control Tower that matters for growth, ops, and design decisions.

---

## 1. What Game360 is (one page)

**Game360** is a **licensed skill-based multiplayer gaming platform** for Africa (Nigeria-first).

| Fact | Detail |
|------|--------|
| Brand | Game360 |
| Legal entity | GAME360, LTD. |
| Jurisdiction | Lagos, Nigeria |
| Regulator | Lagos State Lotteries and Gaming Authority (**LSLGA**) |
| Model | Skill-based matches (not chance / lottery). Players compete; outcomes depend on play. |
| Surfaces | Mobile app (iOS/Android), web play (`game360.games/play`), marketing site (`game360.games`) |

### What players do

1. Create an account, verify identity where required.
2. Fund a **wallet** with **G360 coins** (platform currency).
3. Play skill games vs others (staked or casual): Whot, Ludo, Checkers, Chess, Pool, and more.
4. Optionally join **tournaments**, **live streams**, **friend challenges**, **agencies**, **affiliates**, **ambassadors**.
5. Withdraw winnings through supported payout paths (subject to KYC, limits, and eligibility rules).

### Product pillars (design / growth lens)

- **Social play** — voice/video, friends, live, chat.
- **Fair competition** — stakes, tournaments, disputes, match replay for support.
- **Trust & safety** — KYC, freezes, fraud controls, licensed positioning.
- **Distribution** — agents (agency), affiliates, ambassadors, marketing leads, campaigns.
- **Retention** — Growth OS lifecycle, push/email/WhatsApp, bonuses and streak campaigns.

---

## 2. Systems map (what you will touch)

```
Players (App / Web)
        │
        ▼
┌───────────────────┐     ┌────────────────────┐
│  game_360_service │◄───►│   Control Tower    │  ← you work here daily
│  (core player API)│     │ 360_admin_dashboard│
└───────────────────┘     └─────────┬──────────┘
                                    │
                          ┌─────────▼──────────┐
                          │     Growth OS      │  ← campaigns, inbox, social
                          │ (growth decisions) │
                          └────────────────────┘
```

| System | Audience | Your use |
|--------|----------|----------|
| **Control Tower** | Internal admins | Users, wallet, disputes, campaigns, content, partnerships, settings |
| **Growth OS** | Growth / support / marketing | Lifecycle messaging, inbox, social posts, campaign results, autonomy controls |
| **Player app / web** | End users | What you design for and measure |
| **Marketing site** | Prospects | SEO, signup, cookie consent, PageSense |

You do **not** need to deploy code. You operate products through Control Tower with a role/permissions account.

---

## 3. Day-1 access checklist

Ask the team to provide:

1. **Control Tower URL** (admin dashboard) + login.
2. Role with at least: Growth OS, Content & Marketing, Campaigns, Users (read), Disputes (read), Analytics — expand as needed.
3. Walkthrough of **current live campaigns** and **support inbox channels**.
4. Brand assets / Figma (if any) for product design work.
5. Slack/Telegram channel for approvals and incidents.

**Login tip:** Control Tower uses admin accounts (separate from player accounts). If Google/Firebase sign-in is enabled, use the address that was invited.

---

## 4. Control Tower sidebar — how it’s organized

Sidebar groups (what you see depends on permissions):

### Overview

| Screen | Path | What it’s for |
|--------|------|----------------|
| **Dashboard** | `/` | KPIs: revenue, active users, stakes, system health, alerts, recent activity |

### Operations

| Screen | Path | What it’s for |
|--------|------|----------------|
| **User Management** | `/users` | Find players, open profiles, AI difficulty / cheats (restricted), promo exclusion for duplicate accounts |
| **Games & Tournaments** | `/games` | Catalog, tournaments, match history, **showcase matches**, fair-play rules |
| **Wallet** | `/wallet` | Balances, withdrawals, funding history, financial controls, manual adjustments (restricted) |
| **Financial** | `/financial-report` | Financial report, expenses, investments, salaries, coin calculator |

### Partnership

| Screen | Path | What it’s for |
|--------|------|----------------|
| **Coin trades** | `/marketplace-trades` | P2P / marketplace coin trade rooms and disputes |
| **Agency** | `/agency` | Agent applications, criteria, cashiers, session codes (desk / offline play) |
| **Ambassador** | `/ambassador` | Ambassador roster and payout criteria |
| **Affiliate** | `/affiliate` | Affiliate applications, reports, commission settings |

### Trust & Safety

| Screen | Path | What it’s for |
|--------|------|----------------|
| **Dispute & Support** | `/disputes` | Player disputes, match holds, resolution, replay |
| **Support Macros** | `/support-macros` | Saved reply snippets for support |
| **Security & Compliance** | `/security` | Roles, audit logs, alert rules, compliance |

### Growth (your home base)

| Screen | Path | What it’s for |
|--------|------|----------------|
| **Content & Marketing** | `/content` | Coin packages / promos, **Send Notification**, chat moderation, **marketing leads** |
| **Arena Vote** | `/arena-vote` | In-app vote / community promo surface |
| **Campaigns** | `/campaigns` | Player campaigns (e.g. **Game Streak**, catalog campaigns) — create, standings, payout |
| **Analytics & Reporting** | `/analytics` | Reports and charts |
| **Growth OS** | `/growth` | Lifecycle, campaign results, social, inbox, knowledge, controls |

### System

| Screen | Path | What it’s for |
|--------|------|----------------|
| **Admin Accounts** | `/admin-accounts` | Invite / manage admin users |
| **Settings** | `/settings` | Business, stakes, communications, regional, performance, security, API |

---

## 5. Module deep-dives (operate like this)

### 5.1 Dashboard

**Use when:** Morning pulse, incident check, investor/ops snapshot.

- Scan health / alerts first.
- Drill into revenue, active users, active stakes if numbers look off.
- Escalate system alerts to engineering; don’t “fix” infra from here.

---

### 5.2 User Management

**Use when:** Investigating a player, duplicate promo abuse, support context.

**Typical flow**

1. Search by username / email / phone / ID.
2. Open user sidebar: profile, wallet snapshot, games, referrals, flags.
3. Note **restricted tools** (AI difficulty, Game eye cheats, promo exclusions) — only with special permissions; treat as sensitive.

**Growth / design angle:** Watch cohorts that churn, fail KYC, or never deposit — feed Lifecycle rules and product hypotheses.

---

### 5.3 Games & Tournaments

**Tabs you’ll care about**

| Tab | Ops use | Design use |
|-----|---------|------------|
| Games catalog | Enable/configure games | Surface which games are live |
| Tournaments | Create / manage brackets, prizes | Tournament UX and messaging |
| Match history | Investigate outcomes | Evidence for disputes |
| Match showcase | Schedule announced featured matches | Marketing moments |
| Rules & settings | Fair play, scoring, policies | Copy consistency |

**Showcase:** Schedule → announce → players play → cancel if needed. Good for social proof and content.

---

### 5.4 Wallet (money ops — careful)

**Use when:** Withdrawal queue, funding issues, fraud, manual corrections (restricted).

| Area | What to do |
|------|------------|
| Withdrawal requests | Review → approve / reject with reason; check KYC and eligibility |
| Funding & history | Trace deposits / charges |
| Financial controls | Limits, fraud panels — change only with clear policy |
| Quick actions | Manual deposit, search, freeze (high trust) |
| Manual adjustments | Credit/debit with caps — log why every time |

**Rule of thumb:** Prefer investigation + documented action over silent balance edits. Freezes block abuse while disputes run.

---

### 5.5 Financial report / Expense / Investment / Salary / Coin calculator

Mostly **finance ops**. For growth: use coin calculator when designing promo values (fiat ↔ G360 coins). Don’t post expenses/investments/salaries without finance ownership.

---

### 5.6 Coin trades (marketplace)

P2P coin trade rooms between players (and agents where applicable).  
**Ops:** Monitor stuck trades, open related disputes, watch for fraud patterns.  
**Design:** Friction, trust signals, guidelines pages.

---

### 5.7 Agency (offline / desk distribution)

Agents run **cashiers** and **session codes** so players can play without a full personal funding flow (desk / partner model).

| Sub-area | What you do |
|----------|-------------|
| Applications | Approve / reject agent applications |
| Criteria | Eligibility rules for becoming an agent |
| Agents / cashiers | Monitor activity |
| Session codes | Tickets, ledgers, play history |

**Growth angle:** Agency is a major acquisition/distribution channel. Product design should make agent tooling and player desk UX clear.

---

### 5.8 Ambassador

Creator / promoter program. Manage roster and **payout criteria**. Align with social content and Growth OS Social tab.

---

### 5.9 Affiliate

Referral-style partners with commission settings.

| Sub-area | What you do |
|----------|-------------|
| Applications | Review / approve / reject |
| Reports | Performance |
| Settings | Commission rates and rules |

Affiliate landing/terms live on the marketing site (`/affiliate`, `/affiliate-terms`).

---

### 5.10 Dispute & Support

**Core trust loop.**

1. Open dispute → read parties, category, deadline.
2. Check match winnings hold / trade context.
3. Use **match replay** when available (Watch replay) before ruling.
4. Reply in-thread (player-visible vs internal notes — follow UI labels).
5. Resolve with status + clear resolution text.

**Support Macros:** Save repeated answers (withdrawal timing, KYC steps, how stakes work) so replies stay consistent.

Growth OS **Inbox** handles website/social/Telegram/WhatsApp support; serious account/match issues often still land in **Disputes**.

---

### 5.11 Content & Marketing

**Your primary broadcast tool outside Growth OS lifecycle.**

#### Promotions & bonuses

- Coin packages and promo configs players see when buying coins.
- Design: clarity of bonus %, expiry, eligibility.

#### Notifications & announcements (“Send Notification”)

Channels (as enabled):

- **Push**
- **In-App**
- **Email** (via Zoho Campaigns cutover)
- **WhatsApp** (via Zoho Campaigns templates)

**How to send well**

1. Pick audience segment **or** specific usernames.
2. Write channel-appropriate copy (short for push; richer for email).
3. Set deep link / open path (e.g. `/home`, `/tournaments`, `/fund-wallet-balance`).
4. Send now or schedule; use frequency carefully (daily/weekly).
5. Check status: Draft → Processing → Sent / Failed.

#### In-app messaging / moderation

Flagged chat messages — warn / remove / escalate.

#### Marketing leads

Outreach roster (competitor / prospect leads):

- Import / edit / suppress.
- Send **email** or **WhatsApp** (Zoho) — one channel per send.
- Sync conversions when leads become users.

---

### 5.12 Campaigns (player product campaigns)

Separate from Growth OS lifecycle campaigns.

Examples:

- **Game Streak** — opt-in streak competitions with leaderboard, prizes, T&Cs, social proof for winners, admin payout.
- Other catalog / achievement campaigns as configured.

**Ops flow (Game Streak example)**

1. Create/edit campaign (games, stakes window, prizes, `termsUrl`, social handles).
2. Activate within schedule.
3. Monitor standings.
4. After end: **Preview payout** → **Pay winners** (hides when all prizes paid).
5. Support winners on social-proof submission / T&Cs.

**Design:** Winner celebration, share card, T&C page (`/game-streak-terms`), home banners.

---

### 5.13 Arena Vote

In-product voting / promo engagement. Use for community moments and content calendars.

---

### 5.14 Analytics & Reporting

Build or view reports on growth, play, revenue. Pair with Growth OS Campaigns & results for messaging lift.

---

### 5.15 Growth OS (detailed)

Open **Growth → Growth OS**. Tabs:

| Tab | Purpose | Your actions |
|-----|---------|--------------|
| **Overview** | Health score, pending approvals, inbox stats, anomalies, AI spend, autonomy, daily report, KPIs | Read morning report; regenerate if needed; watch kill switches / acquisition pause |
| **Campaigns & results** | Measurement of lifecycle / growth sends | Inspect lift, conversion, holdouts; don’t confuse “Paused send” with Lifecycle rule pause |
| **Lifecycle** | Rules that trigger messages (push, in-app, email, WhatsApp, SMS) | Create/edit rules, templates, waits, audiences; activate/pause rules; refresh scores if stale |
| **Social** | Connect Meta / TikTok; schedule organic posts | Connect accounts; draft/publish within platform rules |
| **Inbox** | Unified support (web widget, in-app, Telegram, Meta, WhatsApp Cloud) | Answer handoffs; use knowledge; escalate to Disputes when needed |
| **Knowledge** | FAQ / KB for AI + agents | Keep articles accurate — this trains auto-replies |
| **Controls** | Autonomy + inbox auto-send settings | Toggle low-risk auto-execute; set channel auto-reply confidence |

**Approvals:** New copy often needs a human approval. Reused approved templates can batch-send without re-approval. (Approvals tab may be hidden; Overview still shows pending counts.)

**Channels reminder**

| Channel | Typical owner path |
|---------|-------------------|
| Push / In-App | Growth OS Lifecycle **or** Content → Send Notification |
| Email / WhatsApp (marketing) | Zoho via Growth / Content / Leads |
| SMS | Growth user-messages (Termii) where configured |
| Support WhatsApp / Meta / Telegram | Growth OS Inbox (Cloud API — not the same as Zoho blast) |

---

### 5.16 Security & Compliance / Admin Accounts / Settings

- **Security:** roles, audit trail, alerts — ask before changing role permissions.
- **Admin Accounts:** onboarding other admins.
- **Settings:** stakes floors, business flags, communications — product-impacting; change with engineering/product agreement.

---

## 6. First-week learning path (suggested)

### Day 1 — Orientation

- [ ] Log into Control Tower; note which sidebar items you can see.
- [ ] Tour Dashboard + one live player profile (Users).
- [ ] Open Growth OS Overview; read today’s / latest daily report.
- [ ] Play the product as a **test player** on web or app (ask for a sandbox/test account).

### Day 2 — Support & trust

- [ ] Shadow 3–5 disputes (or past resolved ones).
- [ ] Open Inbox; reply to one low-risk handoff with a macro.
- [ ] Skim Support Macros; propose 2 missing FAQs for Knowledge.

### Day 3 — Growth messaging

- [ ] Read Lifecycle rules (active + paused).
- [ ] Draft (don’t send) a push + in-app for a hypothetical reactivation.
- [ ] Review Campaigns & results for one past send (lift / conversion).

### Day 4 — Partnerships & campaigns

- [ ] Walk Agency applications + one session code ledger.
- [ ] Open Affiliate reports + Ambassador criteria.
- [ ] Open Campaigns (Game Streak or live campaign); note standings / payout state.

### Day 5 — Product design intake

- [ ] List top 5 friction points from Inbox + Disputes themes.
- [ ] Pick one surface (signup, deposit, streak, agency desk) and write a one-pager: problem → evidence → proposal → success metric.
- [ ] Align with eng/product on what’s already on the roadmap.

---

## 7. Operating principles

1. **Skill-based & licensed** — public copy must stay accurate (LSLGA, skill not chance).
2. **Least privilege** — don’t use wallet adjust / cheats / freezes casually.
3. **Write the reason** — every reject, freeze, payout, and promo exclusion needs a clear note.
4. **Measure before scaling** — Growth OS holdouts and campaign results exist for this.
5. **One voice** — macros + knowledge base beat improvised support replies.
6. **Design with ops data** — disputes and inbox themes are free user research.
7. **Separate blast vs support WhatsApp** — Zoho campaigns ≠ Inbox Cloud WhatsApp.

---

## 8. Glossary

| Term | Meaning |
|------|---------|
| **G360 coins** | Platform currency for stakes, buys, rewards |
| **Playable vs withdrawable** | Wallet buckets; campaigns/bonuses may restrict spend |
| **Stake** | Coins risked on a match |
| **Opt-in campaign** | Player must join (e.g. Game Streak) before matches count |
| **Lifecycle rule** | Automated message trigger in Growth OS |
| **Holdout** | Users not messaged, used to measure lift |
| **Session code** | Agency/desk ticket for play sessions |
| **Control Tower** | Admin dashboard |
| **Growth OS** | Growth brain + inbox + social inside Control Tower |
| **Zoho Campaigns** | Email / WhatsApp marketing transport |
| **PageSense** | Website analytics (loads after cookie consent) |

---

## 9. Who to ask

| Topic | Owner (fill in names) |
|-------|------------------------|
| Admin access / roles | |
| Wallet / payouts / finance | |
| Disputes policy | |
| Growth OS / messaging | |
| Agency / affiliate deals | |
| Product design priorities | |
| Engineering / incidents | |

---

## 10. Quick links (fill with your environments)

| Resource | URL |
|----------|-----|
| Control Tower (prod) | |
| Control Tower (staging) | |
| Marketing site | https://game360.games |
| Web play | https://game360.games/play |
| Privacy / Terms | https://game360.games/privacy · https://game360.games/terms |
| Game Streak T&Cs | https://game360.games/game-streak-terms |
| Brand / Figma | |

---

## 11. First questions for your kickoff call

1. What are this month’s growth targets (signups, deposits, retention, agency)?
2. Which Lifecycle rules are sacred vs experimental?
3. What’s the current dispute SLA?
4. Which channels are live for marketing (email/WhatsApp/push) vs paused?
5. What product surfaces are we redesigning next?
6. How should Nonye escalate: money risk, abuse, PR, outage?

---

*Document version: 2026-11-12 · Living doc — update when Control Tower modules or Growth OS tabs change.*
