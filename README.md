# Claude Beck — Pitch Package

Everything for the partnership pitch to Beck (@ohsnapitsbeck). Structured as a real production site so once she says yes, you're already 80% deployed.

## File structure

```
Claude Beck/
├── README.md              ← you are here
├── PITCH-NOTES.md         ← what to say in the meeting
├── video.mp4              ← Beck's video (used by landing page)
├── index.html             ← LANDING PAGE (the main page)
├── quiz/
│   └── index.html         ← the quiz
├── compare/
│   └── index.html         ← before/after Gumroad comparison (pitch only)
├── dashboard/
│   └── index.html         ← operator dashboard (pitch only)
└── pitch-docs/
    ├── emails.md          ← 5-email nurture sequence
    └── scoring.md         ← quiz scoring reference
```

## Deployed URL structure

Once you push this to Vercel (via GitHub import), URLs will be:

| URL | What | Audience |
|---|---|---|
| `/` | Landing page | Buyers (production) |
| `/quiz/` | The quiz | Buyers (production) |
| `/compare/` | Before/after comparison | Beck only (pitch) |
| `/dashboard/` | Operator dashboard | Beck/Brian only (pitch) |

The landing page has a yellow "PITCH MODE" bar at the top with links to all four artifacts so Beck can navigate easily during the demo. After she says yes, delete that one bar from each file and you have a clean production site.

## Deploy steps (Vercel + GitHub web upload)

1. Create new GitHub repo (private is fine) at github.com → New repository → name it `claude-beck`
2. Drag the contents of this folder into GitHub's web uploader
3. Go to vercel.com, hit Refresh on the repo list, find `claude-beck`, click Import
4. Framework Preset: "Other" — Deploy
5. Done. You get a URL like `claude-beck-significant721.vercel.app`

## To run locally (optional)

Just open `index.html` in a browser. Cross-page links may not all work without a server, but each page renders standalone. For full local testing, use `python3 -m http.server` from this folder and visit `localhost:8000`.

## After Beck says yes

1. Remove the `.pitch-nav` block from `index.html`, `quiz/index.html`, `compare/index.html`, `dashboard/index.html`
2. Add real Stripe checkout link to the pricing CTA (`href="#pricing"` → `href="https://buy.stripe.com/..."`)
3. Connect quiz email capture to ConvertKit/Beehiiv (currently just a placeholder submit)
4. Replace placeholder testimonials on landing page with real ones from past buyers
5. Buy a custom domain (`snaptoit.app` or similar) and point at Vercel
6. Move `/compare/` and `/dashboard/` behind a basic password (Vercel supports this)
