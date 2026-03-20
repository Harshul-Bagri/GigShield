# 🛡️ GigShield — AI-Powered Parametric Income Insurance for Food Delivery Partners

> *"When the rain stops your rides, GigShield covers your income."*

**Guidewire DEVTrails 2026 | Team Submission | Phase 1**

---

## 📌 Table of Contents
1. [The Problem](#the-problem)
2. [Our Solution](#our-solution)
3. [Persona & Scenarios](#persona--scenarios)
4. [Application Workflow](#application-workflow)
5. [Weekly Premium Model](#weekly-premium-model)
6. [Parametric Triggers](#parametric-triggers)
7. [Platform Choice Justification](#platform-choice-justification)
8. [AI/ML Integration Plan](#aiml-integration-plan)
9. [Tech Stack](#tech-stack)
10. [Development Plan](#development-plan)
11. [Financial Model](#financial-model)

---

## The Problem

India has over **12 million food delivery partners** working for platforms like Zomato and Swiggy. These workers earn entirely on a **per-delivery, per-hour basis** — averaging ₹600–₹900/day in metro cities. They operate with zero financial safety nets.

When external disruptions hit — a cyclone in Chennai, a red-alert AQI day in Delhi, a sudden political bandh in Mumbai — deliveries stop. The platform pauses operations. The worker earns ₹0 for the day. They still owe rent, EMIs, and school fees.

**The gap:** No insurance product exists today that covers this exact scenario — income lost due to *external environmental or social disruptions* — at a price point a delivery worker can afford.

---

## Our Solution

**GigShield** is an AI-enabled parametric income insurance platform built exclusively for Zomato and Swiggy delivery partners.

### How it works in one sentence:
> When a verified external disruption (heavy rain, severe AQI, curfew) crosses a predefined threshold in a worker's operating zone, GigShield automatically detects the trigger, validates the claim, and transfers lost income directly to their UPI wallet — **zero paperwork, zero waiting.**

### Key Differentiators:
- **Zero-touch claims** — no worker ever needs to file a claim manually
- **Hyperlocal risk scoring** — premiums are calculated per city zone, not just per city
- **Weekly pricing** — aligned with how gig workers actually think about money
- **Fraud-resistant by design** — parametric model means payouts are tied to verifiable data, not worker testimony

---

## Persona & Scenarios

### Primary Persona: Rajesh, Swiggy Delivery Partner, Bengaluru

- **Age:** 28 | **City:** Bengaluru (Koramangala–Indiranagar zone)
- **Earnings:** ₹700/day average, works 6 days/week (~₹4,200/week)
- **Peak hours:** 12–2 PM and 7–10 PM
- **Pain point:** Loses 2–3 days of income during monsoon season (June–September) every year with zero recourse

### Scenario 1 — Heavy Rainfall Trigger
> It's July. Bengaluru receives 85mm of rain in 6 hours. Swiggy pauses operations in Koramangala. Rajesh parks his bike. Without GigShield, he loses ₹700. With GigShield, by 11 PM the system has already detected the IMD rainfall alert, cross-validated with Swiggy's zone-pause API signal, approved the claim automatically, and transferred ₹560 (80% of daily average) to his UPI ID.

### Scenario 2 — Severe AQI Trigger
> November. Delhi AQI hits 420 (Hazardous). GRAP Stage IV restrictions are imposed. Zomato advises partners to stay home. Meena, a Zomato partner in Dwarka, gets an automatic payout for 4 hours of lost income without opening the app once.

### Scenario 3 — Unplanned Curfew / Bandh
> A sudden bandh is called overnight in Pune. Local social media confirms road closures by 7 AM. GigShield's NLP engine detects the bandh via Twitter/X keyword clusters and official government alerts. Delivery partner Suresh receives an alert: "Your zone is disruption-covered today. Income protection activated."

### Scenario 4 — Platform Outage (App Crash)
> Swiggy faces a backend outage for 3 hours during dinner peak. GigShield detects the platform API going silent across a region and cross-validates with Downdetector signals. Workers in active status at outage time receive a partial income protection payout.

---

## Application Workflow

```
┌─────────────────────────────────────────────────────────────────────┐
│                        GIGSHIELD PLATFORM                           │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  [ONBOARDING]                                                       │
│  Worker registers → Links Zomato/Swiggy ID → Verifies UPI          │
│  → AI Risk Engine scores their zone → Weekly premium quoted        │
│  → Worker selects coverage tier → Policy activated                 │
│                                                                     │
│  [MONITORING — 24/7 BACKGROUND]                                     │
│  Weather APIs → AQI APIs → Govt Alert Feeds → Social NLP          │
│  → Platform uptime signals → Zone-level aggregation               │
│                                                                     │
│  [TRIGGER DETECTED]                                                 │
│  Threshold crossed → Fraud engine validates → Claim auto-created   │
│  → Worker notified via SMS + App → Payout initiated via UPI        │
│                                                                     │
│  [DASHBOARD]                                                        │
│  Worker: Weekly coverage status, earnings protected, claim history  │
│  Admin: Live disruption map, loss ratios, fraud flags, payouts     │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Detailed Flow:

**Step 1 — Onboarding (< 3 minutes)**
- Mobile-friendly web form: Name, city, delivery platform, zone/area, UPI ID
- Platform ID verification (simulated API handshake with Zomato/Swiggy)
- AI risk scoring runs in background using zone historical data
- Weekly premium displayed with coverage breakdown

**Step 2 — Policy Activation**
- Worker selects from 3 coverage tiers (Basic / Standard / Premium)
- Weekly payment deducted via UPI AutoPay or Zomato Pay integration
- Policy card generated with unique GigShield ID

**Step 3 — Real-Time Monitoring**
- Continuous polling of disruption data APIs by zone
- ML model evaluates multi-signal confluence (not single-API dependent)
- Alert thresholds defined per city, per disruption type

**Step 4 — Automatic Claim**
- Trigger crossed → system logs event with timestamp + API evidence
- Fraud checks run (location active? policy active? not a duplicate?)
- Claim auto-approved or flagged for manual review
- UPI transfer initiated within 15 minutes

**Step 5 — Payout & Communication**
- SMS + in-app notification: "₹420 credited to your UPI for today's rain disruption"
- Claim receipt generated with disruption evidence attached
- Worker dashboard updated

---

## Weekly Premium Model

### Philosophy
Gig workers don't think monthly. They think week-to-week. A ₹500/month premium feels abstract. A ₹120/week premium feels manageable — it's the cost of 2 cups of chai per day.

### Coverage Tiers

| Tier | Weekly Premium | Daily Coverage Cap | Disruption Hours Covered |
|------|---------------|-------------------|------------------------|
| **Basic** | ₹79/week | ₹400/day | 4 hrs/day, max 2 days/week |
| **Standard** | ₹129/week | ₹650/day | 6 hrs/day, max 3 days/week |
| **Premium** | ₹199/week | ₹900/day | 8 hrs/day, max 5 days/week |

### Dynamic Premium Calculation

The base premium is adjusted by an **AI Risk Multiplier** (0.7x – 1.4x) based on:

```
Final Weekly Premium = Base Tier Price × Zone Risk Score × Seasonal Factor × Claim History Factor

Where:
- Zone Risk Score     = Historical disruption frequency in worker's operating zone (0.7–1.3)
- Seasonal Factor     = Monsoon/winter pollution season uplift (1.0–1.2)
- Claim History Factor = Reduces over time for low-claim workers (0.85–1.0)
```

**Example:**
> Rajesh in Koramangala (high flood-risk zone) subscribes to Standard tier in July (peak monsoon):
> ₹129 × 1.25 (zone risk) × 1.15 (monsoon season) × 1.0 = **₹185/week**

> Same worker in January (dry season, low risk zone):
> ₹129 × 0.85 × 1.0 × 0.92 = **₹101/week**

This makes the model actuarially sound while being transparent to the worker.

---

## Parametric Triggers

All triggers are **objective, verifiable, and API-sourced** — no worker testimony required.

| # | Trigger | Source API | Threshold | Payout |
|---|---------|-----------|-----------|--------|
| 1 | **Heavy Rainfall** | IMD API / OpenWeatherMap | >50mm in 3 hours in worker's pin code | 70% of daily avg per disrupted hour |
| 2 | **Severe AQI** | CPCB AQI API / IQAir | AQI > 350 (Severe) in worker's city zone | 60% of daily avg for full day |
| 3 | **Flood Alert** | NDMA / State Disaster API | Official flood/waterlogging alert for zone | 80% of daily avg, up to 2 days |
| 4 | **Curfew / Bandh** | Govt. alert feeds + NLP on social signals | Official notification OR >80% keyword confidence | 75% of daily avg |
| 5 | **Platform Outage** | Zomato/Swiggy uptime monitor (Downdetector + mock API) | >2 hrs downtime in region during peak hours | 50% of hourly avg × hours lost |

### Multi-Signal Validation
No single API signal triggers a payout. The fraud engine requires **at least 2 corroborating signals** before approving any claim:

```
Rainfall Payout Approved IF:
  IMD rainfall > threshold  AND
  (Worker GPS was in active zone OR Platform order-rate dropped > 60%)
```

---

## Platform Choice Justification

**We chose a Web App (React/Next.js) with a Progressive Web App (PWA) layer.**

| Factor | Reasoning |
|--------|-----------|
| **Accessibility** | Food delivery workers use a wide range of Android phones, many low-end. A PWA reaches all of them without app store friction |
| **No install required** | Workers can onboard via a WhatsApp link → browser → done |
| **Offline support** | PWA caching means workers can check their policy status even on 2G |
| **Admin dashboard** | Web is optimal for the insurer-side analytics dashboard |
| **Development speed** | Single codebase serves both worker-facing and admin interfaces |

The worker-facing UI is **mobile-first**, designed for one-thumb navigation and tested for low-literacy contexts (icon-heavy, minimal text, regional language support via i18n).

---

## AI/ML Integration Plan

### 1. Dynamic Premium Calculation — Risk Scoring Model
- **Algorithm:** Gradient Boosted Trees (XGBoost) trained on historical weather, AQI, and disruption event data per city zone
- **Input features:** Zone ID, month/season, historical disruption frequency, platform order drop rate, worker tenure
- **Output:** Zone Risk Score (float, 0.7–1.4)
- **Training data:** 3 years of IMD historical rainfall, CPCB AQI data, Zomato zone-level order pattern simulations
- **Retraining:** Weekly, as new disruption events are logged

### 2. Fraud Detection Engine — Anomaly Detection
- **Algorithm:** Isolation Forest + Rule-based layer
- **Signals monitored:**
  - Worker GPS location at time of claimed disruption (were they actually in the zone?)
  - Claim frequency vs. historical baseline (sudden spike = flag)
  - Cross-worker correlation (if 200 workers in a zone claim, it's real; if 1 worker claims and no others do, flag it)
  - Time-of-claim vs. disruption window (claiming 12 hours after disruption ended = suspicious)
- **Output:** Fraud Risk Score (0–100). Score > 70 → manual review queue

### 3. Social Signal NLP — Bandh/Curfew Detection
- **Algorithm:** Fine-tuned BERT classifier (or zero-shot via Claude API for Phase 1 prototype)
- **Data source:** Twitter/X keyword search on "bandh", "curfew", "road closed" + city name
- **Output:** Disruption confidence score (0–1). Threshold: 0.80 for trigger activation
- **Fallback:** Government alert feed scraper (NDMA, state disaster management sites)

### 4. Predictive Risk Alert — Worker Notification
- **Algorithm:** Time-series forecasting (Prophet / LSTM) on weather patterns
- **Purpose:** 48-hour advance warning to workers: "High disruption risk this weekend — your coverage is active"
- **Benefit:** Increases trust, reduces support queries, differentiates GigShield from competitors

### 5. Platform Outage Detection
- **Method:** Synthetic monitoring — automated ping to Zomato/Swiggy order endpoints every 5 minutes
- **Validation:** Cross-reference with Downdetector API + social signal spike
- **Output:** Outage confirmed / not confirmed per region

---

## Tech Stack

### Frontend
| Layer | Technology |
|-------|-----------|
| Framework | Next.js 14 (App Router) |
| UI Library | Tailwind CSS + shadcn/ui |
| State Management | Zustand |
| Maps | Leaflet.js (zone visualization) |
| Charts | Recharts (admin dashboard) |
| PWA | next-pwa |
| i18n | next-intl (Hindi, Tamil, Telugu support) |

### Backend
| Layer | Technology |
|-------|-----------|
| API Framework | FastAPI (Python) — primary backend |
| Auth | JWT + OTP via Twilio/MSG91 |
| Database | PostgreSQL (policies, claims, workers) |
| Cache | Redis (real-time disruption state) |
| Queue | Celery + Redis (async claim processing) |
| Scheduler | APScheduler (trigger polling every 5 min) |

### AI/ML
| Component | Technology |
|-----------|-----------|
| Risk Scoring | XGBoost (scikit-learn) |
| Fraud Detection | Isolation Forest (scikit-learn) |
| NLP / Bandh Detection | Claude API (zero-shot) / HuggingFace BERT |
| Forecasting | Facebook Prophet |
| ML Serving | FastAPI endpoint (model loaded in memory) |

### Integrations (Phase 1: mocked; Phase 2–3: live/sandbox)
| Service | API / Method |
|---------|-------------|
| Weather | OpenWeatherMap API (free tier) |
| AQI | OpenAQ API (free) / CPCB mock |
| Disaster Alerts | NDMA RSS feed scraper |
| Payment | Razorpay Test Mode |
| Platform Data | Mock API simulating Zomato/Swiggy zone-pause signals |
| Social NLP | Twitter API v2 (free tier) + Claude API |

### Infrastructure
| Layer | Technology |
|-------|-----------|
| Hosting | Vercel (frontend) + Railway / Render (backend) |
| CI/CD | GitHub Actions |
| Monitoring | Sentry (errors) + Grafana (metrics) |
| Version Control | GitHub (monorepo) |

---

## Development Plan

### Phase 1 — Seed (March 4–20): Ideation & Foundation ✅
- [x] Problem research and persona definition
- [x] Weekly premium model design
- [x] Parametric trigger selection and threshold definition
- [x] Tech stack finalization
- [x] GitHub repository setup with this README
- [x] System architecture diagram
- [x] 2-minute strategy video

**Phase 1 Prototype Scope:**
- Static Next.js frontend: Landing page + Onboarding flow (UI only)
- Mock premium calculator (formula-driven, no ML yet)
- Basic risk score display based on city + season inputs

---

### Phase 2 — Scale (March 21–April 4): Automation & Protection
**Target: 4-star submission**

**Week 3:**
- [ ] Worker registration + OTP auth (backend live)
- [ ] PostgreSQL schema: workers, policies, claims, zones
- [ ] Onboarding flow connected to backend
- [ ] Weekly premium calculator (XGBoost model integrated)
- [ ] 3 live trigger monitors: Rainfall, AQI, Platform Outage

**Week 4:**
- [ ] Automated claim creation pipeline
- [ ] Fraud detection engine (Isolation Forest, rule-based layer)
- [ ] Mock UPI payout integration (Razorpay test mode)
- [ ] Worker dashboard (policy status, claim history)
- [ ] 2-minute demo video

---

### Phase 3 — Soar (April 5–17): Scale & Optimise
**Target: 5-star submission**

**Week 5:**
- [ ] Advanced fraud: GPS spoofing detection, cross-worker correlation
- [ ] Bandh/Curfew NLP engine (Claude API + Twitter signals)
- [ ] Flood alert integration (NDMA feed)
- [ ] Predictive risk alert system (Prophet forecasting)
- [ ] Full payout simulation with receipt generation

**Week 6:**
- [ ] Admin/Insurer dashboard (loss ratios, disruption heatmap, fraud queue)
- [ ] Multi-language support (Hindi minimum)
- [ ] Load testing + performance optimization
- [ ] 5-minute final demo video
- [ ] Pitch deck (PDF)

---

## Financial Model

### Unit Economics (per worker, per week)

```
Average Weekly Premium Collected : ₹140
Expected Weekly Claim Cost        : ₹85   (based on ~0.6 disruption days/week avg)
Gross Margin per Worker per Week  : ₹55   (~39%)

Target User Base (Year 1)         : 50,000 workers
Annual Premium Revenue            : ₹140 × 50,000 × 52 = ₹36.4 Cr
Annual Claims Payout              : ~₹22.1 Cr
Gross Profit                      : ~₹14.3 Cr
```

### Why This Works Actuarially
- Parametric model eliminates claims processing cost (zero adjusters)
- Weather/AQI triggers are geographically aggregated — one event = many valid claims = no individual fraud motivation
- Weekly churn is low once workers experience their first payout
- Platform partnerships (Zomato/Swiggy) as distribution channel = near-zero CAC at scale

---

## Repository Structure

```
gigshield/
├── frontend/                  # Next.js 14 web app
│   ├── app/
│   │   ├── onboarding/        # Worker registration flow
│   │   ├── dashboard/         # Worker dashboard
│   │   ├── admin/             # Insurer analytics dashboard
│   │   └── api/               # Next.js API routes
│   ├── components/
│   └── public/
├── backend/                   # FastAPI Python backend
│   ├── api/
│   │   ├── workers.py
│   │   ├── policies.py
│   │   ├── claims.py
│   │   └── triggers.py
│   ├── ml/
│   │   ├── risk_scorer.py     # XGBoost premium model
│   │   ├── fraud_detector.py  # Isolation Forest
│   │   └── nlp_engine.py      # Bandh/curfew detection
│   ├── services/
│   │   ├── weather.py         # OpenWeatherMap integration
│   │   ├── aqi.py             # OpenAQ integration
│   │   ├── payout.py          # Razorpay integration
│   │   └── scheduler.py       # Trigger polling
│   └── models/                # Trained ML model artifacts
├── docs/
│   ├── architecture.png
│   └── demo-video-link.md
└── README.md
```

---

## Demo Video
📹 **[Video Link — Phase 1 Strategy Walkthrough]** *(to be added)*

---

## Team
**GigShield | Guidewire DEVTrails 2026**
Built with React/Next.js · FastAPI · Python ML · Claude API

---

*"India's 12 million delivery workers deserve a safety net as fast as the deliveries they make."*