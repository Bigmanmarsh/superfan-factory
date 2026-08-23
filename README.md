# 🛸 Superfan Factory

**Your AI community copilot — built entirely on the [FanBase MCP](https://fanbase.gg/features/mcp).**

It watches your community around the clock, spots superfans worth celebrating and fans about to drift away, drafts posts in your voice across every platform you connect, hunts the web for opportunities you care about — and **you approve everything.**

> *FanBase built the engine. We built the chauffeur.*

## 👀 Try it (30 seconds)

**→ [bigmanmarsh.github.io/superfan-factory](https://bigmanmarsh.github.io/superfan-factory/)**

1. Click **Connect your FanBase** — works with any FanBase account
2. See *your own* community: superfans, fading fans, alerts, drafts
3. Talk to it: *"what needs my attention today?"*

No signup. No backend. Your tokens never leave your browser.

## 🧠 What it does

| | |
|---|---|
| 💜 **Superfan radar** | Most engaged fans, ranked live — one click drafts shoutouts naming them by handle |
| 💤 **Win-back watch** | Catches fans going quiet and drafts re-engagement posts before they're gone |
| 🖨️ **One idea, every platform** | Drop one thought → AI drafts it natively for X, Instagram, TikTok, YouTube, Discord |
| 📅 **Event brain** | Pin mints/AMAs/giveaways → live countdowns, AI-drafted hype, **server-side scheduled publishing** (posts go out even if you never open the app) |
| 🌐 **Open-web hunters** | Stakeout searches on Telegram (`/hunt creator jobs`) sweep Hacker News + live job boards around the clock — linked finds delivered to your pocket |
| 📲 **Telegram remote control** | Full command menu: `/hunt` `/queue` `/draft` `/fans` `/numbers` `/mood` `/nightshift` — your community, from your pocket |
| 🌙 **Night shift** | Every morning at 08:00: fresh posts + replies pre-drafted into your approval queue, announced by Telegram. *It worked while you slept.* |
| 💬 **Ask Factory** | A chat that actually knows your people: *"catch me up on @fan"*, *"what's coming up?"*, *"how's the vibe?"* |
| ⚖️ **Approval queue** | It drafts. You approve. Nothing publishes without you. |

## 🏗️ Architecture — zero backend, by design

```
🖥️ THE FACE  ·  this repo (GitHub Pages)        ⚙️ THE HEART  ·  github.com/Bigmanmarsh/superfan-heart
   static HTML · OAuth in-browser                  GitHub Actions · beats every 5 min, free
   dashboard · chat · hunts · approvals            24/7 hounds · night shift · Telegram pings
                        └──── 🧠 THE BRAIN: FanBase MCP ────┘
        CRM · fan histories · activity · analytics · AI skills · drafts · scheduling
                                + 🌐 open-web sources (HN Algolia · RemoteOK)
```

- The app talks **directly** to the MCP from the browser — the MCP *is* the backend
- The Heart is an always-on agent twin on free GitHub runners: hounds every 5 minutes, night-shift drafting at 08:00, everything delivered to Telegram
- FanBase's own approval queue is the shared state between them — the Heart drafts overnight, you approve with coffee

**MCP tools in active use (17 of 27):** `list_crm` · `get_fan_activity` · `query_activity` · `activity_summary` · `lookup_socials` · `list_conversations` · `get_account_analytics` · `get_analytics_trend` · `list_platform_connections` · `list_recommendations` · `update_recommendation` · `post_content` · `trigger_skill` (post-creators ×5, sentiment ×4) · `generate_reply_recommendations` · `generate_brand_voice` / `update_brand_voice`

## 🔐 Trust

- OAuth 2.1 + PKCE via FanBase login — no API keys, nothing to leak
- Tokens live in your browser (Face) or sealed repo secrets (Heart) — never on any server of ours
- Publishes only with your explicit approval · revoke anytime in FanBase → Settings → AI Connections

## 📰 Built for the XBorg × FanBase MCP builder competition (Aug 2026)

Scored on their rubric — **usefulness**: a daily retention engine that catches churn, buy-intent comments and real opportunities; **shows what the MCP can do**: 17 tools choreographed across reads, writes, AI skills and scheduling; **reusability**: any FanBase user connects in one click, and anyone can deploy their own copy by uploading one HTML file.

MIT License. Made with 🛸 and questionable amounts of sleep.
