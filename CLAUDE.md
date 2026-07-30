# LIVO — Master Context File
> This file is the single source of truth for all Claude sessions working in this repo.
> Read this first. Then read the CLAUDE.md in whichever folder you are working in.

---

## 1. What Is LIVO?

**LIVO** is a residential and commercial home services brand serving the **Lower Mainland, BC**.
It is the consumer-facing brand of **LandEx Construction Ltd.**

- **Website:** livoland.com
- **CEO / Founder:** Ali Makki Javid
- **Parent Company:** LandEx Construction Ltd. (hazardous materials abatement — separate operation)
- **Headquarters:** Port Coquitlam, BC, Canada

LIVO exists to provide homeowners, Airbnb hosts, landlords, and businesses with reliable, professional home services under one brand. The goal is a multi-division operation that scales across BC and eventually into Alberta and the US.

---

## 2. The 6 Divisions

| Division                  | Folder                        | Key Market              |
|---------------------------|-------------------------------|-------------------------|
| Power Washing & Windows   | `divisions/power-washing/`    | Homeowners, strata      |
| Carpet & Upholstery       | `divisions/carpet-upholstery/`| Homeowners, Airbnb      |
| Interior Cleaning         | `divisions/interior-cleaning/`| Recurring, move in/out  |
| Junk Removal              | `divisions/junk-removal/`     | Homeowners, landlords   |
| Airbnb Turnover           | `divisions/airbnb-turnover/`  | STR hosts               |
| Commercial Cleanup        | `divisions/commercial-cleanup/`| Offices, retail, strata |

Each division has its own `CLAUDE.md` with scope, SOPs, and target customer details.

---

## 3. How LIVO Works (Business Model)

### Customer Journey
```
Customer visits livoland.com
        ↓
Selects service → Fills booking form
        ↓
Quote generated (instant or manual)
        ↓
Job confirmed → Team dispatched
        ↓
Service completed → Photo report sent
        ↓
Invoice → Payment
        ↓
Follow-up → Recurring booking or review request
```

### Revenue Model
- **One-time jobs:** Single service bookings (most junk removal, deep cleans, power washing)
- **Recurring contracts:** Weekly/bi-weekly cleaning, commercial maintenance
- **Package deals:** Bundle 2+ services at a discount
- **Referral program:** 10% discount for clients referred through LandEx Construction

### Pricing Strategy
- Competitive with Lower Mainland market rates
- Transparent pricing on website where possible
- Custom quotes for large or complex jobs
- All current rates → `docs/pricing.md`

---

## 4. Brand Identity

Full brand details → `brand/CLAUDE.md`

**Quick reference:**
- Background: Dark charcoal `#1C1C1C`
- Accent: Lime green `#C8FF00`
- Text: Soft lavender `#9D7FE8`
- Tone: Clean, confident, friendly. Short sentences. No jargon.

---

## 5. Business Strategy

### Geographic Expansion (in order)
1. ✅ Lower Mainland, BC (current)
2. Fraser Valley, BC
3. Victoria, BC
4. Okanagan, BC
5. Alberta
6. United States

### Growth Strategy
- **Lead with Airbnb Turnover** — fastest growing segment, high repeat frequency
- **Upsell bundles** — combine Interior Cleaning + Carpet + Power Washing
- **LandEx referral pipeline** — LandEx abatement clients often need cleanup after remediation → warm LIVO leads
- **Google reviews** — primary trust signal; request after every completed job
- **Recurring revenue** — push all cleaning clients toward recurring contracts

### Competitive Advantage
- Multi-service under one brand (vs. single-trade operators)
- Professional documentation (photo reports, checklists)
- Fast response and same-day turnaround (especially Airbnb)
- Backed by LandEx (established, licensed, insured)

---

## 6. Repo Structure & Rules

```
livo/
├── CLAUDE.md              ← This file (root bible — always read first)
├── README.md              ← Public-facing repo description
├── CORTEX.html            ← R&D / strategy portal (do not modify unless instructed)
│
├── brand/                 ← Colors, fonts, logo, design tokens
│   └── CLAUDE.md
│
├── content/               ← Website copy, blog posts, marketing text
│   └── CLAUDE.md
│
├── dev/                   ← Tech stack, deploy, code conventions
│   └── CLAUDE.md
│
├── divisions/             ← One folder per service line
│   ├── CLAUDE.md
│   ├── power-washing/
│   ├── carpet-upholstery/
│   ├── interior-cleaning/
│   ├── junk-removal/
│   ├── airbnb-turnover/
│   └── commercial-cleanup/
│
├── docs/                  ← Pricing, contracts, policies
│   └── CLAUDE.md
│
├── livo/                  ← Website / app build files
│   └── CLAUDE.md
│
└── notes/                 ← Internal notes, ideas, research
    └── CLAUDE.md
```

---

## 7. Claude Rules (Read Every Session)

1. **Always read this file first.** Then read the `CLAUDE.md` in the folder you are working in.
2. **Never guess prices.** All rates are in `docs/pricing.md`.
3. **Never change brand colors or fonts** without explicit instruction. See `brand/CLAUDE.md`.
4. **Never modify `CORTEX.html`** unless Ali explicitly says to.
5. **When making any change**, also update the relevant `CLAUDE.md` in the same commit.
6. **Referral discount is 10%** — applies to all services for clients referred by LandEx. Flag in system.
7. **LIVO ≠ LandEx.** LIVO is the consumer services brand. LandEx is hazardous materials abatement. Keep them separate.
8. **Commit both the change AND the CLAUDE.md update together** — one commit, one message.
9. **Git:** Always check `git status` before committing. Push to `origin/main` only after review.
10. **Do not install packages** without confirmation from Ali.

---

## 8. Changelog

### 2026-07-30 — Knowledge layer added to CORTEX portal
- **What changed:** `CORTEX.html` gained a Knowledge section. It fetches the repo's own `.md` files over relative paths, renders them (headings, tables, lists, blockquotes, code, links), and provides full-text search across every registered file. Sidebar has a new **Knowledge** group filtering by Livo / LandEx / Vorx / Group. Each file shows its `Last-Modified` date and an "Edit on GitHub" link. Version bumped v1.1 → v1.2.
- **Why:** The portal was a launchpad of links only. All the competitor, pricing, and equipment intelligence lived in `.md` files the portal never read, so Cortex could not be used to actually think or make decisions.
- **File registry:** 23 files across Livo (12), LandEx (2), Vorx (2), Group (7). Registry lives in the `KB_FILES` array in `CORTEX.html`. **Adding a new `.md` requires adding it to `KB_FILES`** or it will not appear in the portal.
- **Branch:** `staging` (not yet merged to main)
- **Pending:** Awaiting Ali's approval to promote to main. Note PR #1 (competitor dossier) is still open from `staging` → `main`; merging it will now also bring this change.
- **Known issues:**
  - `notes/livo-competitor-dossier.md` resolves only after PR #1 merges. Until then the reader shows a "not on main yet" notice for it.
  - Repo visibility: repo is **public**. Competitor intel and pricing rate cards are publicly readable. Ali to switch to private (requires GitHub Pro for Pages to keep serving).
- **Notes:** Rule 4 above ("never modify CORTEX.html unless Ali explicitly says to") was satisfied — Ali explicitly authorised this build.

### Content gaps identified 2026-07-30
Files on `main` are thin stubs and do not reflect work done in chat sessions:
| File | Size on main | Status |
|---|---|---|
| `notes/competitors.md` | 1.3 KB | Stub — ~12 rows, superseded by the dossier |
| `docs/pricing.md` | 2.0 KB | Rate cards present, no margin floors, no dynamic-pricing rules |
| `docs/equipment.md` | 1.6 KB | Partial — cumulative equipment log not merged in |
| `cortex/references/03-livo-services.md` | 0.9 KB | Summary only |

**Cortex update protocol:** every independent project session (Livo, Vorx, LandEx, Ascentra, STR) must end by emitting a `CORTEX UPDATE` block naming the target file and the exact content to append, dated. Without this, work stays trapped in chat and Cortex goes stale.
