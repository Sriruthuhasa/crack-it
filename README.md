# ⚡ Crack It

An AI job-hunt copilot that combines discovery, materials, outreach, interview prep, and tracking into one pipeline — folding together the best ideas from GiraffyReach, AIApply, and Tsenta.

**Live app:** enabled via GitHub Pages (see the repo's Pages settings for the URL).

## What's real in this build
- **Job Radar** — pulls *real, current* job postings live from official ATS APIs (Greenhouse & Ashby), ranked against your profile. No scraping, no backend.
- **ATS Scanner** — real client-side keyword-coverage scoring against any job description.
- **Match ranking** — every live role scored against your résumé keywords.
- **Tracker** — drag-and-drop pipeline board, saved in your browser (localStorage).
- **Apply →** — opens the genuine job posting to complete on the company's site.

## Not yet wired (needs a backend / API key)
- AI résumé & cover-letter generation (Claude API)
- Recruiter outreach (Gmail OAuth + open/click tracking)
- Auto-submit to ATSes (Playwright + CAPTCHA handling — human-in-the-loop)

## Add more companies
Edit the `BOARDS` array near the top of the `<script>` in `index.html`. One line per company board:

```js
{p:"greenhouse", token:"notion", co:"Notion", color:"#000000"},
{p:"ashby",      token:"linear", co:"Linear", color:"#5E6AD2"},
{p:"lever",      token:"someco", co:"SomeCo", color:"#333333"},
```

## Run locally
```bash
python -m http.server 8765
# open http://localhost:8765/
```
Serve it over `http://` — opening the file directly (`file://`) makes the browser block the ATS API calls (CORS).

## Tech
Single self-contained HTML file. Vanilla JS, no build step, no dependencies. Google Fonts only.
