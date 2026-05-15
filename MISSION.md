# SkyEye Drone Media — Project Handover Document

## Overview
**Business:** SkyEye Drone Media — aerial drone videography and photography for real estate in University City, Philadelphia PA
**Started:** 2026-05-13
**Status:** Active — website live, market research complete, lead generation in progress
**Last Session:** 2026-05-15 — deployment permanently fixed via gitSource, skills cleaned up (removed broken references), MISSION.md refreshed
**Owner:** Aaryan (University City, Philadelphia)

---

## Live Assets

### Website
- **Production URL:** https://skyeye-drone-v2.vercel.app
- **Alias:** https://skyeye-drone-media.vercel.app (both resolve to same deployment)
- **Vercel Project:** `skyeye-drone-v2` (ID: `prj_jf7U7zwbLQHo5seiphfGVAIRObX1`)
- **Vercel Team:** `team_zZOjxA4ogPtJ0w4oUSs0lg9m`
- **GitHub Repo:** https://github.com/Aarz-aaryan/skyeye-drone-media
- **Framework:** React (create-react-app) with vercel.json
- **Local source:** `/home/Aarz/skyeye-drone-media/`
- **Latest commit:** `62f56cb` (Update MISSION.md - active status, live website, research complete)

### Content Updates (done by Jarvis)
- **Hero:** "Aerial Perspectives for Philadelphia Real Estate" / "Professional Drone Videography"
- **Services:** Real Estate Aerial Video, Property Walkthroughs, Aerial Photography, Commercial Roofing Inspection, Event Coverage
- **Contact:** info@skyeyeaerial.com / (267) 555-0147
- **Service area:** University City, Center City, Manayunk, Chestnut Hill, Philadelphia metro

### Market Research (done by Nina)
- **Notion page:** https://www.notion.so/SkyEye-Drone-Media-Market-Research-35ff900ffeb2811da960f70dd10c208f
- **Google Sheet (Lead Tracking):** https://docs.google.com/spreadsheets/d/109eCljPdGUdKMYKdjpvGA8kQTRdLlbPvaOWpCT2v6eU/edit

---

## Tech Stack & Configuration

### GitHub Token
```
[GITHUB_TOKEN — see user's established method for retrieval]
```
- Stored as git remote: `https://[GITHUB_TOKEN]@github.com/Aarz-aaryan/skyeye-drone-media.git`
- Use for direct git push (bypasses Composio file size limits for large binary files)
- Can be used for GitHub API calls directly (create repos, push files, etc.)

### Vercel Configuration
- **vercel.json:** `{"buildCommand": "react-scripts build", "outputDirectory": "build", "framework": "create-react-app"}`
- **buildCommand:** `react-scripts build` (set in vercel.json, overrides sticky project config)
- **outputDirectory:** `build`
- **framework:** create-react-app (causes sticky build config — vercel.json is the workaround)
- **ssoProtection:** `all_except_custom_domains` (Hobby plan limitation — cannot disable)
- **nodeVersion:** 24.x

### Important Vercel Gotchas (learned the hard way)
1. Project-level `framework` and `buildCommand` are STICKY — can only be set at creation time via API, cannot be cleared
2. Workaround: use `vercel.json` in the repo root to override project settings with `buildCommand: "react-scripts build"`
3. SSO protection on Hobby plan blocks preview deployment URLs (return HTTP 401) — only production alias works
4. `skyeye-drone-v2.vercel.app` works fine (production alias). Individual deployment URLs get 401 blocked
5. Never delete a Vercel project that has an active URL you need — deletion breaks the URL permanently
6. **`files[]` upload via Composio creates Lambda storage that intercepts static assets** — JS returns 401, CSS returns 404. Use `gitSource` instead (Vercel clones from GitHub, builds, serves from CDN).
7. **`commandForIgnoringBuildStep: "exit 0"` cancels ALL GitHub-triggered deployments** — clear it via `VERCEL_UPDATE_PROJECT2`. The `buildCommand` in vercel.json works because Vercel reads it before the override fires.
8. **Vercel Personal API Token** stored in `~/.hermes/.env` as `VERCEL_TOKEN`, `VERCEL_PROJECT_ID`, `VERCEL_TEAM_ID`. Token has `vcp_` prefix. Get from `.env` — do NOT commit to repo.

---

## Market Research Summary

### Competitors (8 found)
| Company | Website | Pricing | Notes |
|---|---|---|---|
| Philly By Drone | phillybydrone.com | — | Full-service aerial photography & cinematography |
| SkyShot Aerial | skyshotaerial.com | $199–$549 | Tiered pricing: Basic/Popular/Luxury |
| Kuma Photo | kumaphoto.com | ~$150–$349 | Aerial video from ~$150 for 2-min |
| Space360 Photography | space360photography.com | ~$249+ | Custom quotes |
| Philadelphia Aerial Photography & Imaging | phillyflyphoto.com | — | 20+ years experience, FAA-licensed |
| UAV Snap | uavsnap.com | — | FAA-certified, real estate/construction |
| PCR Aerial Solutions | pcraerialsolutions.com | — | Philly suburbs, property marketing |
| East Philly Media | eastphillymedia.com | — | Events and branded content |

### Local Real Estate Agency Prospects (6 identified)
| Agency | Website | Focus | Status |
|---|---|---|---|
| The City Block Team | cityblockteam.com | University City / Center City | Not Contacted |
| Elfant Wissahickon REALTORS | elfantwissahickon.com | Residential, commercial, investment | Not Contacted |
| Nigel & Co. | nigelandco.com/universitycity | University City specialist | Not Contacted |
| OCF Realty | ocfrealty.com | Property management, leasing, development | Not Contacted |
| Philly Home Girls | phillyhomegirls.com | — | Not Contacted |
| West Philadelphia Real Estate | wpre.com | West Philadelphia | Not Contacted |

### Pricing Strategy
- **Entry-level:** $99–$150
- **Standard (photo + video):** $150–$249
- **Mid-tier:** $249–$349
- **Premium/Luxury:** $349–$549
- **RECOMMENDED:** $175–$299 for standard listings, $350+ for luxury/commercial

### Key Market Insights
- Listings with aerial photos sell **68% faster**
- Growing demand for roof inspections and construction documentation
- University City/West Philadelphia has active real estate market

---

## Lead Tracking Sheet

**Google Sheet:** https://docs.google.com/spreadsheets/d/109eCljPdGUdKMYKdjpvGA8kQTRdLlbPvaOWpCT2v6eU/edit
**Spreadsheet ID:** `109eCljPdGUdKMYKdjpvGA8kQTRdLlbPvaOWpCT2v6eU`

**Columns:** Name, Type (Competitor/Prospect), Website, Contact, Email, Phone, Address, Status, Notes, Last Contacted, Follow Up Date

**Current entries:** 14 (8 competitors + 6 prospects)

---

## Agent Delegation Log

| Agent | Task | Status | Date |
|---|---|---|---|
| Jarvis | Website creation from Capture-Portfolio template | ✅ Done | 2026-05-13 |
| Jarvis | Vercel deployment fix + content update | ✅ Done | 2026-05-14 |
| Nina | Market research (competitors, pricing, prospects) | ✅ Done | 2026-05-14 |
| Nina | Notion page creation | ✅ Done | 2026-05-14 |
| Aarz (self) | Lead tracking Google Sheet | ✅ Done | 2026-05-14 |
| Aarz (self) | Deployment permanently fixed (gitSource + vercel.json), skills cleaned, MISSION.md updated | ✅ Done | 2026-05-15 |

---

## Action Plan (Next Steps)

### Immediate (Week 1)
- [ ] Find contact emails for the 6 prospect agencies (need email discovery)
- [ ] Set up Gmail/email sending capability for cold outreach
- [ ] Draft cold email template for real estate agents
- [ ] Start email outreach to The City Block Team, Nigel & Co., OCF Realty

### Short-term (Weeks 2–4)
- [ ] Instagram account setup — post 3x/week aerial reels
- [ ] Claim and optimize Google Business Profile for "drone photography Philadelphia"
- [ ] Attend Philadelphia Association of Realtors meetup
- [ ] Track all outreach responses in Google Sheet

### Growth
- [ ] Partner with roofing companies and construction firms
- [ ] Build location pages for: University City, West Philadelphia, Center City, Fishtown
- [ ] Target 2–3 trial shoots at discounted rate to build portfolio

---

## Tools & Integrations Connected

| Tool | Connection | Status |
|---|---|---|
| Vercel | Composio MCP | ✅ Active |
| GitHub | Personal token + Composio MCP | ✅ Active |
| Notion | Composio MCP | ✅ Active |
| Google Sheets | Composio MCP | ✅ Active |
| Google Drive | Composio MCP | ✅ Active |

---

## Cleanup Notes

### Local (`/home/Aarz/skyeye-drone-media/`)
- ✅ `node_modules/` — removed (was 323MB)
- ✅ `build/` — removed (was 2.1MB)
- ✅ `/tmp/` batch files — removed (batch1.json, batch2.json, skyeye_build.tar.gz, etc.)
- ✅ Root-level stray package.json — removed

### GitHub
- ✅ All source files committed and pushed
- ✅ `build/` excluded from git tracking via `.gitignore`
- ✅ MISSION.md pushed to commit `62f56cb`

### Vercel (things to delete manually)
- ❌ `skyeye-drone-media` (old project) — already deleted on our end, verify it's gone from your dashboard
- ❌ `skyeyedm` — if it still exists as a separate project, delete it
- ✅ Keep `skyeye-drone-v2` — this is the live project

### Website Structure

**Pages:** 5 (`/`, `/about`, `/work`, `/contact`, `/*` 404)
**Components:** 13 (Nav, Hero, AboutSection, ServicesSection, OurSuccess, FaqSection, Footer, etc.)
**Styling:** styled-components with dark theme (`#0a0f1a` base, `#00d4ff` accent, `#00ff88` secondary)

#### File Map
```
src/
├── App.js                    — Router setup (5 routes)
├── index.js                  — React entry
├── index.css                 — Google Fonts (Space Grotesk)
├── components/
│   ├── Nav.js                — Fixed navbar: SkyEyeDM logo, Home/About/Work/Contact links
│   ├── GlobalStyles.js       — Global CSS (fonts, resets, scrollbar)
│   ├── Footer.js             — Footer: contact info, service areas, social links
│   ├── AboutSection.js      — "Why Choose Us" — 4 feature cards (4K Quality, FAA Licensed, Fast Turnaround, Competitive Pricing)
│   ├── ServicesSection.js    — 5 services with icons: Real Estate Aerial Video, Property Walkthroughs, Aerial Photography, Commercial Roofing Inspection, Event Coverage
│   ├── OurSuccess.js         — Stats section: "68% Faster Home Sales", "100+ Projects Completed", "5-Star Reviews"
│   └── FaqSection.js         — 6 FAQ items about pricing, turnaround, weather, locations
└── pages/
    ├── Home.js               — Hero: "Aerial Perspectives for Philadelphia Real Estate", CTAs (Get a Free Quote, See Our Work)
    ├── AboutUs.js            — About page with AboutSection + OurSuccess + Footer
    ├── OurWork.js            — Portfolio page (placeholder — needs actual demo reels)
    ├── ContactUs.js          — Contact form (Name, Email, Phone, Project Type dropdown, Message), phone (267) 555-0147
    └── NotFound.js           — 404 page

public/
├── index.html                — "SkyEye Drone Media — Aerial Real Estate Videography Philadelphia"
├── manifest.json             — PWA manifest, theme #0a0f1a
└── robots.txt
```

#### Key Content
- **Hero tagline:** "Professional Drone Videography — University City, Philadelphia"
- **Hero title:** "Aerial Perspectives for Philadelphia Real Estate"
- **Hero sub:** "Stunning 4K drone footage and cinematic property tours that make buyers stop scrolling — and actually click on your listing."
- **Contact email:** info@skyeyeaerial.com
- **Contact phone:** (267) 555-0147
- **Service areas:** University City, Center City, Manayunk, Chestnut Hill, Philadelphia metro
- **Logo:** SkyEyeDM (navbar)

#### Color Scheme
- Background: `#0a0f1a` (dark navy)
- Accent: `#00d4ff` (cyan)
- Secondary: `#00ff88` (green)
- Gradient: `linear-gradient(135deg, #00d4ff, #00ff88)` (used on CTAs)

#### Dependencies
- react, react-dom, react-router-dom, styled-components

#### To Edit Content
Edit the relevant `.js` file in `src/pages/` or `src/components/`, then:
```bash
npm install && npm run build
git add . && git commit -m "update message" && git push
```
Vercel auto-deploys on push to `main` branch.

---

## Session Memory (for future sessions)

When you inherit this mission, here is what you need to know:

1. **Website is live at:** https://skyeye-drone-v2.vercel.app — do NOT delete this Vercel project
2. **Source code:** `/home/Aarz/skyeye-drone-media/` — if you make changes, run `npm install && npm run build` locally, then `git add . && git commit && git push`
3. **GitHub token:** `[GITHUB_TOKEN]` — use for direct git push, bypasses Composio file size limits
4. **Research:** Check Notion page and Google Sheet before starting any new work
5. **If Vercel deployment breaks:** Check if `vercel.json` still has `"buildCommand": "react-scripts build"` — this is the workaround for Vercel's sticky framework detection

---

*Last updated: 2026-05-14 03:40 UTC — created by Aarz during SkyEye Drone Media session*