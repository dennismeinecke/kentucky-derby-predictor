🌹 Kentucky Derby AI Predictor
> AI-powered handicapping for the 152nd Run for the Roses — May 2, 2026 · Churchill Downs
Built with Next.js and Claude AI. Analyzes all 20 horses using Beyer Speed Figures, post position history, running style, trainer/jockey angles, and track conditions. API key stays server-side — never exposed to the browser.
---
Features
🐎 Full Field View
All 20 confirmed starters with post positions, morning-line odds, jockeys, trainers, and racing styles
Beyer Speed Figure displayed per horse
Market-implied win probability calculated from current odds
Click any horse to instantly run AI handicapping analysis
Track condition selector (Fast / Good / Muddy / Sloppy / Yielding)
🔮 Horse Analysis
AI win probability vs market-implied probability — edge in percentage points
Edge rating (1–10 scale)
Key factors — what makes this horse dangerous
Concerns — what could go wrong
Track condition impact — how today's surface affects this horse specifically
Recommended bet types — Win, Place, Exacta, etc.
One-click log to bet tracker
🏆 Full Race Analysis
Hit AI Full Race Analysis and Claude analyzes all 20 horses together:
Predicted winner
Exacta, Trifecta, Superfecta picks
Longshot of the race with reasoning
Pace scenario — how the early race will unfold
Track bias — which running style benefits from conditions
Horses to avoid
Top picks ranked by edge score
📊 Bet Tracker
Log Win / Place / Show / Exacta / Trifecta / Superfecta bets
Units, odds, and notes per bet
Running W/L record, net units, and ROI
Mark Won / Lost / Pending inline
Auto-populated from prediction screen
---
Quick Start
1. Clone
```bash
git clone https://github.com/yourusername/kentucky-derby-predictor.git
cd kentucky-derby-predictor
```
2. Install
```bash
npm install
```
3. Configure
```bash
cp .env.example .env.local
```
Open `.env.local` and add your Anthropic API key:
```
ANTHROPIC_API_KEY=sk-ant-your-key-here
```
Get a free key at console.anthropic.com.
4. Run
```bash
npm run dev
```
Open http://localhost:3000.
---
Architecture
```
kentucky-derby-predictor/
├── pages/
│   ├── index.js              # Main app — Field, Predict, Analysis, Tracker views
│   ├── _app.js               # Next.js app wrapper
│   └── api/
│       ├── predict.js        # Server-side: single horse AI analysis
│       └── analyze-race.js   # Server-side: full 20-horse field analysis
├── styles/
│   └── globals.css
├── .env.example              # Safe to commit — template only
├── .env.local                # ← Your key goes here (gitignored)
└── next.config.js
```
API Routes
Route	Method	Description
`/api/predict`	POST	Claude analyzes a single horse — win prob, edge, factors, concerns
`/api/analyze-race`	POST	Claude analyzes the full field — winner, exotics, pace scenario
Both routes read `ANTHROPIC_API_KEY` from `process.env` — the key is never sent to the browser or included in the client bundle.
---
2026 Field
The full confirmed 20-horse field is embedded in `pages/index.js` with post positions, odds, jockey/trainer, racing style, Beyer figures, and key notes updated after all scratches (Right to Party, Silent Tactic, Fulleffort replaced by Robusta, Great White, Ocelli).
Post	Horse	Odds	Style	Beyer
1	Renegade	5-1	Closer	98
2	Albus	30-1	Stalker	88
3	Intrepido	20-1	Presser	91
4	Litmus Test	15-1	Stalker	93
5	Robusta	50-1	Closer	84
6	Commandment	6-1	Stalker	101
7	Danon Bourbon	30-1	Presser	89
8	So Happy	6-1	Closer	97
9	The Puma	5-1	Closer	99
10	Wonder Dean	20-1	Closer	90
11	Incredibolt	20-1	Presser	92
12	Chief Wallabee	8-1	Stalker	95
13	Great White	50-1	Closer	82
14	Potente	20-1	Presser	90
15	Emerging Market	15-1	Closer	94
16	Pavlovian	30-1	Closer	87
17	Further Ado	6-1	Stalker	107
18	Golden Tempo	30-1	Presser	88
19	Six Speed	50-1	Closer	83
20	Ocelli	50-1	Closer	87
---
Deploy to Vercel
```bash
npm install -g vercel
vercel
```
Add `ANTHROPIC_API_KEY` in the Vercel dashboard under Settings → Environment Variables.
---
Race Details
Event: 152nd Kentucky Derby — Run for the Roses
Date: Saturday, May 2, 2026
Venue: Churchill Downs, Louisville, KY
Post Time: 6:57 PM ET
TV: NBC / Peacock (2:30 PM ET coverage start)
Weather: Mostly sunny, high 61°F, calm winds, fast track
---
Built By
Dennis Meinecke — AI Consultant & Enterprise Technology Executive  
linkedin.com/in/aipo · dennis.r.meinecke@gmail.com  
DRM Consulting LLC
---
Disclaimer
This application is for entertainment and educational purposes. It demonstrates AI-powered analysis techniques using publicly available racing data. Always gamble responsibly. Past performance does not guarantee future results.
