# 🚀 Insight AI SEO Marketing SaaS

[![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?logo=typescript)](https://www.typescriptlang.org/)
[![Convex](https://img.shields.io/badge/Convex-Realtime-orange)](https://convex.dev/)
[![Clerk](https://img.shields.io/badge/Clerk-Auth%20%26%20Billing-purple)](https://clerk.com/)
[![Stripe](https://img.shields.io/badge/Stripe-Payments-635BFF?logo=stripe)](https://stripe.com/)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o-412991?logo=openai)](https://openai.com/)
[![Bright Data](https://img.shields.io/badge/Bright%20Data-Web%20Scraping-00A67E)](https://brightdata.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-v4-38BDF8?logo=tailwindcss)](https://tailwindcss.com/)
[![shadcn/ui](https://img.shields.io/badge/shadcn/ui-Components-black)](https://ui.shadcn.com/)

**Generate beautiful, data-driven SEO reports in seconds using AI, real-time scraping, and modern full-stack architecture.**

This project demonstrates how to build a **production-ready SEO marketing SaaS** using **Next.js 16**, **Convex**, **Clerk billing**, **Bright Data scraping**, and **AI-powered analysis with OpenAI**.

---

## 🧠 What This App Does

Think of this as an **AI-powered SEO analyst**.

You enter a company, product, or website → the system:
1. Scrapes real SERP data using Bright Data
2. Processes results with AI using structured prompts
3. Generates a validated SEO report
4. Streams progress in real time
5. Lets Pro users **chat with the report** for deeper insights

---

## ✨ Core Features

- 🔐 **Authentication & Billing** — Clerk auth with Starter / Pro plans (Stripe-powered)
- 📊 **AI SEO Report Generation** — Structured, evidence-backed SEO analysis
- 🌐 **Professional Web Scraping** — Bright Data SERP & Perplexity integration
- ⚡ **Real-Time Progress Tracking** — Live job status updates via Convex
- 🤖 **AI SEO Assistant (Pro)** — Chat with reports using contextual AI + web search
- 📈 **Beautiful Dashboards** — Charts and insights with Recharts
- 🔁 **Smart Retry Logic** — Retry failed analyses without re-scraping expensive data

---

## 🖼️ Screenshots

| Homepage | Features |
|--------|----------|
| ![](public/screenshots/home.png) | ![](public/screenshots/features.png) |

| Pricing | Create New Report |
|--------|------------------|
| ![](public/screenshots/pricing.png) | ![](public/screenshots/create-new-report.png) |

| AI Analysis | AI Assistant |
|------------|-------------|
| ![](public/screenshots/ai-analysis.png) | ![](public/screenshots/ai-assistant.png) |

| Keywords & Themes | Report Categories |
|------------------|------------------|
| ![](public/screenshots/keywords.png) | ![](public/screenshots/report-categories.png) |

| Source Statistics | Report Status |
|------------------|---------------|
| ![](public/screenshots/report-stats.png) | ![](public/screenshots/report-status.png) |

---

## 🧩 Project Structure

```txt
app/
  page.tsx                 # Marketing homepage
  dashboard/
    page.tsx               # Report creation & management
    report/[id]/page.tsx   # Report status & loading
    summary/page.tsx       # Full SEO analysis
    ui/                    # Report visualization components
  api/chat/route.ts        # AI chat endpoint
components/
  AIChat.tsx               # Pro chat interface
  ReportsTable.tsx         # Dashboard listing
  ConvexProviderWithClerk.tsx
convex/
  schema.ts                # Database schema
  scrapingJobs.ts          # Job orchestration
  analysis.ts              # AI workflows
  http.ts                  # Bright Data webhooks
actions/
  startScraping.ts         # Start scraping jobs
  retryAnalysis.ts         # Smart retry logic
lib/
  seo-schema.ts            # Zod schemas
  seo-utils.ts             # SEO helpers
middleware.ts              # Clerk route protection
```

---

## 🔄 How It Works

### Data Flow
1. User submits entity + country
2. `startScraping` creates a Convex job
3. Bright Data scrapes SERP data
4. Webhook delivers raw data to Convex
5. OpenAI processes structured prompts
6. SEO report is validated & stored
7. Pro users chat with the report

### Background Processing
- Long-running jobs via **Convex schedulers**
- Real-time updates via reactive queries
- Retry without re-scraping raw data

---

## 🧠 AI Architecture

- **Structured Outputs** using Zod schemas
- **Evidence-based insights** (quotes + URLs)
- **Context-aware AI chat**
- **Web search augmentation** (Pro feature)
- **Vercel AI SDK** for streaming & type safety

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- pnpm
- Accounts:
  - Clerk
  - Convex
  - Bright Data
  - OpenAI
  - Vercel

### Step-by-Step Setup

```bash
git clone https://github.com/johnsonr84/ai-seo-marketing-saas
cd ai-seo-marketing-saas
pnpm install
cp .env.example .env.local
```

Fill in `.env.local`:

```env
# Clerk
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=

# Convex
CONVEX_DEPLOYMENT=
NEXT_PUBLIC_CONVEX_URL=

# Bright Data
BRIGHTDATA_API_KEY=

# OpenAI
OPENAI_API_KEY=

# Vercel AI Gateway
AI_GATEWAY_API_KEY=
```

Start development:

```bash
pnpm dev
npx convex dev
```

---

## 🧯 Common Issues

- ❌ Missing env vars → double-check `.env.local`
- 🔑 Clerk JWT → ensure `convex` JWT template exists
- 🌐 Webhooks → verify Bright Data can reach `/api/webhook`
- 🤖 Rate limits → monitor OpenAI usage
- 🔁 Convex schema → run `npx convex dev`

---

## 👨‍💻 Author

**Robert Johnson**  
Full-Stack Software Engineer  
🌐 https://robertjohnsonportfolio.com

---
