# e-Delegate - Electronic Delegation Log Platform

> **The open-source electronic delegation log and site qualification platform for clinical research - ICH GCP E6(R2) compliant, 21 CFR Part 11 ready.**

[![Live App](https://img.shields.io/badge/Live%20App-e--delegate.qrx--jay.workers.dev-teal?logo=cloudflare&logoColor=white)](https://e-delegate.qrx-jay.workers.dev)
[![Nokware Research](https://img.shields.io/badge/By-Nokware%20Research%20Solutions-navy)](https://nokware-site.pages.dev)
[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](LICENSE)

---

## Live Demo

**https://e-delegate.qrx-jay.workers.dev**

Click **Demo Login** on the login screen - no account needed. All data is stored locally in your browser.

---

## What Is e-Delegate?

e-Delegate replaces paper-based delegation logs, training binders, and PDF workarounds with a structured, inspection-ready electronic system. It is designed from the ground up to meet the delegation-of-authority requirements of **ICH GCP E6(R2)** and the electronic records and signature requirements of **21 CFR Part 11**.

Built by a Senior Clinical Research Associate with 14+ years of Phase I-IV trial experience - for the research sites, coordinators, and monitors who live inside these systems every day.

---

## Key Features

| Feature | Description |
|---|---|
| **Digital Delegation Logs** | Structured, versioned records capturing who, what, when, and under which protocol version |
| **21 CFR Part 11 E-Signatures** | Identity verification, meaning-of-signature capture, tamper-evident timestamps |
| **Role-Based Access Control** | Granular permissions for PIs, sub-investigators, coordinators, monitors, and sponsors |
| **GCP Training Tracking** | Personnel certificates linked directly to delegation entries with expiry alerts |
| **Immutable Audit Trail** | Every action logged with timestamp, user, and change delta - FDA inspection ready |
| **Multi-Protocol Support** | Multiple protocols per site with version-controlled amendment propagation |
| **Dashboard** | Live compliance stats - active protocols, training compliance %, pending signatures |
| **Export / Print** | Print-ready delegation records formatted for regulatory binders |

---

## App Sections

- Login Screen - Demo login or authenticated access
- Dashboard - Compliance stats, recent activity, training expiry alerts
- Delegation Log - Full CRUD for delegation entries + e-signature workflow
- Protocols - Protocol cards with delegation summaries
- Personnel - Staff management + GCP certification tracking
- Training Records - Certificate upload, expiry dates, compliance progress bar
- Audit Trail - Immutable, timestamped log of all system actions
- Settings - Site info, user profile, notification preferences

---

## Compliance

| Standard | Status |
|---|---|
| ICH GCP E6(R2) - Section 4.1.5 Delegation | Structurally aligned |
| 21 CFR Part 11 - Electronic Records | Audit trail, access controls, versioning |
| 21 CFR Part 11 - Electronic Signatures | Identity, meaning, timestamp, tamper-evidence |
| FDA Inspection Readiness | Export, print, and binder-format output |

---

## Tech Stack (Full-Stack Version)

The demo runs as a self-contained HTML app with localStorage. The production version is a full-stack monorepo:

| Layer | Technology |
|---|---|
| **Frontend** | React 18, TypeScript, Vite |
| **State / Data** | TanStack Query v5, Axios |
| **Routing** | React Router v6 |
| **Styling** | Tailwind CSS |
| **Backend** | Node.js |
| **Database** | PostgreSQL |
| **CI/CD** | GitHub Actions |
| **Hosting (demo)** | Cloudflare Workers / Pages |
| **License** | MIT |

---

## Local Development (Demo / Static Version)

No installation needed for the standalone demo:

    git clone https://github.com/nokware-research/e-delegate.git
    cd e-delegate

    Option 1 - Python
    python3 -m http.server 8080
    Open http://localhost:8080

    Option 2 - Node
    npx serve .
    Open the URL shown in your terminal

---

## Running the Full-Stack Version

Requirements: Node.js 20+, PostgreSQL 15+

    git clone https://github.com/nokware-research/e-delegate.git
    cd e-delegate
    npm run install:all
    cp server/.env.example server/.env
    npm run db:migrate --workspace=server
    npm run dev

    Server runs at: http://localhost:3001
    Client runs at: http://localhost:5173

---

## Build for Production

    npm run build
    npm run start

---

## Deploy to Render.com (Free Tier)

**Step 1 - Create a PostgreSQL database**
- Render > New > PostgreSQL > Free plan > Create
- Copy the Internal Database URL

**Step 2 - Deploy the API server**
- Render > New > Web Service > connect this repo
- Root Directory: server | Build: npm install && npm run build | Start: npm run start
- Add env var: DATABASE_URL = paste from Step 1

**Step 3 - Deploy the React client**
- Render > New > Static Site > connect this repo
- Root Directory: client | Build: npm install && npm run build | Publish: dist
- Add env var: VITE_API_URL = your server URL from Step 2

---

## Contributing

Contributions are welcome - whether you write code, write tests, improve documentation, or bring clinical domain expertise.

    git checkout -b feature/your-feature-name
    git commit -m "feat: describe what you built"
    git push origin feature/your-feature-name
    Open a Pull Request

**What we especially need:**
- Rails / Node.js backend engineers
- Clinical research coordinators with UX feedback
- Regulatory affairs professionals for compliance review
- Translators for multi-language consent support

---

## Repo Structure (Full-Stack)

    e-delegate/
    client/                 React 18 + TypeScript + Vite frontend
      src/
        components/         Reusable UI components
        pages/              Route-level page components
        hooks/              TanStack Query hooks
        types/              TypeScript interfaces
      package.json
      vite.config.ts
    server/                 Node.js API server
      src/
        routes/             API route handlers
        models/             Database models
        middleware/         Auth, validation, audit logging
      package.json
    index.html              Standalone SPA demo (no backend required)
    package.json            Root workspace config
    README.md

---

## Contact & Links

| Resource | URL |
|---|---|
| **Live Demo** | https://e-delegate.qrx-jay.workers.dev |
| **Marketing Site** | https://nokware-site.pages.dev |
| **GitHub Org** | https://github.com/nokware-research |
| **Email** | inquiries_requests@nokware-research.org |
| **Phone** | +1 (214) 473-4241 |

---

## License

MIT - free to use, modify, and deploy. See LICENSE for details.

---

Designed and built by Kojo A. Quansah Jr., PharmD - Senior Clinical Research Associate, clinical trial technologist, and Founder of Nokware Research Solutions. 14+ years driving Phase I-IV trials across oncology, ophthalmology, immunology, infectious disease, and neuroscience.
