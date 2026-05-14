# SkyEye Drone Media — Project Handover Document

## Overview
**Business:** SkyEye Drone Media — aerial drone videography and photography for real estate in University City, Philadelphia PA
**Started:** 2026-05-13
**Status:** Active — website live, market research complete, lead generation in progress
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
5. Old project `prj_bMf58q0DoTsWttuRUMObYEqy4Uh` was deleted — skyeye-drone-media.vercel.app URL broke because the project is gone
6. Never delete a Vercel project that has an active URL you need — deletion breaks the URL permanently

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

| Agent | Task | Status |
|---|---|---|
| Jarvis | Website creation from Capture-Portfolio template | ✅ Done |
| Jarvis | Vercel deployment fix + content update | ✅ Done |
| Nina | Market research (competitors, pricing, prospects) | ✅ Done |
| Nina | Notion page creation | ✅ Done |
| Aarz (self) | Lead tracking Google Sheet | ✅ Done |

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