# Principal Plumbers — Demo Business Profile

A mobile-first, hyperlocal **business profile site** for Principal Plumbers (Durban, KwaZulu-Natal), built as a single self-contained `index.html` — no build step, no dependencies, instant GitHub Pages hosting.

**Live demo:** `https://jacobseatlholo.github.io/principalplumbers-demo/` (after enabling GitHub Pages)

---

## Features

| Feature | Implementation |
|---|---|
| **Mobile-first profile** | Google-Business-Profile-style layout: hero, quick-action bar, services, areas, reviews, hours, FAQ, sticky mobile CTA |
| **Structured data (SEO/AI)** | JSON-LD `Plumber` + `FAQPage` schema graph with NAP, geo, opening hours, `areaServed` (12 suburbs), offer catalog, ratings, WhatsApp `potentialAction` — ready for Google, Bing and AI assistants |
| **WhatsApp lead capture** | 3-step quote wizard (service → urgency → contact) composes a *structured* WhatsApp message with a unique lead reference (`PP-XXXXXX`) and opens it pre-filled via `wa.me` deep link. Every lead arrives fully organised in WhatsApp Business |
| **Automated first contact** | The structured pre-filled message lets you set up WhatsApp Business greeting/quick replies that auto-confirm; leads are also archived in browser `localStorage` (`pp_leads`) |
| **German translation** | Full EN/DE toggle (🌐 button) covering every string incl. the WhatsApp message; language auto-detected from browser, persisted in `localStorage` |
| **Live open/closed status** | Real-time "Open now · until 17:00" pill computed from trading hours |

## Quick start

Open `index.html` in a browser — that's it. Deploy by pushing to GitHub and enabling **Settings → Pages → Deploy from branch → main / (root)**.

## ⚠️ Replace demo contact details before going live

Open `index.html` and edit the `CONFIG` block (search for `DEMO CONFIGURATION`):

```js
const CONFIG = {
  businessName: 'Principal Plumbers',
  phoneDisplay: '082 010 0123',      // ← real display number
  phoneIntl:    '+27820100123',      // ← real tel: number
  waNumber:     '27820100123',       // ← WhatsApp Business number (intl, digits only!)
  email:        'info@principalplumbers.co.za',
  ...
};
```

Also update the phone numbers in the JSON-LD block (`"telephone": ...`), the `tel:` links, and the demo review content as needed. Trading hours live in the `HOURS` object right below the FAQ data.

## Recommended WhatsApp Business automation setup

1. **Greeting message** (auto-sent on first contact):
   > "Hi! Thanks for contacting Principal Plumbers 🙏 Your reference number is noted — a plumber will confirm your quote shortly. For burst pipes tap *Emergency* below."
2. **Quick replies:** `/geyser`, `/drain`, `/emergency` with price ranges
3. **Labels:** create a *New Lead* label and label every message containing "Request PP-" so leads are trackable in WhatsApp Business
4. **Away message** for after-hours, pointing emergencies to the 24/7 line

## File structure

```
├── index.html    # the entire site (HTML + CSS + JS, zero dependencies)
├── .nojekyll     # tells GitHub Pages to serve files as-is
└── README.md
```

---
*Demo built for client preview. Reviews, ratings and stats are illustrative placeholders.*
