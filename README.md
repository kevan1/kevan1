# Hi, I'm Kevin Anrique 👋

**Full-stack & DevOps engineer** from Argentina, based in Berlin. I build products end to end: mobile and web apps, the backend and database behind them, and the infrastructure, CI and tests that keep them shippable. I'm currently **Founder & CTO of [Cachin](https://cachin.app)**, a LATAM-first payments app, and I'm learning ML by shipping LLM features into real products. **3× hackathon winner** (Solana, Midnight, Cardano). Member of **[Superteam Argentina](https://github.com/SuperteamAR)**. Solana is my main chain.

## What I do

- **Product engineering, end to end.** TypeScript across Next.js (App Router, RSC, Server Actions), Expo / React Native and Node/Express, from the spec to the App Store build.
- **Data & security by default.** Postgres/Supabase with Row-Level Security, roles from trusted JWT claims, DB-level constraints and quotas, and audit trails. I test the security boundary instead of just trusting it.
- **DevOps.** Docker, GitHub Actions, Vercel, EAS builds, GCP (Cloud SQL / GCS), Linux ops, Ansible-managed workstations. My background is infra and IT operations: CI/CD, monitoring, ELK, AWS/GCP.
- **Applied AI.** LLM agents and structured extraction with Gemini, RAG with LangChain + OpenAI + vector DB, and spec-driven, test-first workflows with AI coding agents.
- **Web3, Solana first.** Solana is my main chain: USDC payments, Solana Pay, fee sponsorship and liquid staking (STEAK.NET). I've also shipped on Cardano (Aiken), Midnight (zero-knowledge / Compact) and Base, with Pyth oracles and embedded wallets and passkeys (Privy, Turnkey).

## Tech stack

| Area | Tools I've shipped with |
|---|---|
| Languages | TypeScript, JavaScript, SQL, Shell, Aiken, Compact, C/C++, Java |
| Frontend | Next.js 15/16, React 19, Tailwind CSS v4, shadcn/ui · Radix, Zustand, D3 (zoom) |
| Mobile | Expo / React Native, Expo Router, EAS, TestFlight |
| Backend | Node.js, Express, Vercel Functions, Supabase (Auth, Storage, Realtime, Edge Functions), Firebase |
| Data | PostgreSQL, Supabase RLS, Drizzle, Kysely, pg-boss, Redis (Upstash), Astra DB (vectors) |
| Testing | Vitest, Playwright (e2e, performance, Lighthouse, axe), Supertest, Testcontainers, pgTAP |
| DevOps / Cloud | Docker, GitHub Actions, Vercel, GCP, Ansible, Linux |
| AI / LLM | Gemini 2.5, OpenAI, LangChain (RAG), Vercel AI SDK |
| Web3 | Solana, USDC, Solana Pay, Privy, Turnkey, Cardano (Aiken, Lucid, Maestro), Midnight, Base MiniKit, viem |

## Featured projects

### Public

- **[AdMouse Flasher](https://github.com/kevan1/admouse-flasher)** · [live](https://admouse-flasher.vercel.app)
  An accessible, browser-based configurator and firmware flasher for a single-button ATtiny85 controller. I implemented the Micronucleus USB bootloader protocol in TypeScript over **WebUSB**, patched the firmware config block (version, action, checksum) in the browser, and wrote reproducible ATtiny85 firmware builds. Tests cover firmware patching, the protocol and the UI. Nothing leaves the browser.
- **[STEAK.NET](https://github.com/kevan1/steak-net)** · [live](https://steak.net)
  A liquid staking dApp for STEAKSOL on Solana. Users swap SOL or any liquid staking token into STEAKSOL with best-route quotes from Sanctum and Jupiter. Built with Next.js 14, TypeScript, Tailwind and the Solana Wallet Adapter.
- **[Guards](https://github.com/kevan1/guards-ui)** · [live](https://guards-ui.vercel.app)
  An oracle-aware treasury risk dashboard built at Pythathon Buenos Aires with Nico Fernandez ([@f0x1777](https://github.com/f0x1777)). It scores a treasury against a risk ladder using Pyth price, EMA and confidence data, and simulates protective swaps. This repo is the frontend showcase and runs on simulated data.
- **[kevan.ar](https://github.com/kevan1/kevan.ar)** · [live](https://kevan.ar)
  My portfolio, built with Next.js and MDX. It includes a **RAG chatbot** over the site content (LangChain, OpenAI embeddings, Astra DB, Upstash) and a Resend contact flow. Embedding generation runs separately from the production build.
- **[Midnight ZK-KYC](https://github.com/kevan1/midnight-zk-kyc)**
  A privacy-preserving KYC platform on the Midnight Network. Users prove age, country and liveness through **zero-knowledge proofs** and on-chain commitments without revealing the underlying data. Built with Next.js 16, TypeScript and the Midnight Wallet SDK.
- **[dotfiles](https://github.com/kevan1/dotfiles)** / **[mac setup playbook](https://github.com/kevan1/kevan-setup-mac-playbook)**
  My workstation as code: zsh config and Ansible provisioning.

### Case studies (private repos)

- **Cachin: LATAM QR payments** · [cachin.app](https://cachin.app)
  I'm the solo founder and built the Expo/React Native app (iOS, Android and TestFlight beta). Users fund globally, scan local QR codes, review FX and fees, and pay. It uses Privy embedded wallets with passkeys, USDC settlement on Solana, and Vercel API routes for wallet provisioning, fee sponsorship (paymaster), identity, push notifications (Helius webhooks) and payment-provider orchestration, plus Sumsub KYC and Crisp support. I also built a companion **CachinPOS** app that generates Solana Pay USDC QRs for merchants.
- **SectorTwin: industrial operations map**
  A local-first, role-based 2D "digital shadow" of an industrial process line: an ISA-95 asset model, an interactive SVG map (D3 zoom, layers, search), private documents, and simulated telemetry that marks data stale and then offline. Next.js 16 + Supabase with **default-deny RLS** tested per role (anonymous/viewer/editor/admin) using pgTAP. CSV import validates a preview first and commits all-or-nothing in one transaction. The audit log is immutable. Quality gates cover Playwright e2e, performance budgets (INP < 200 ms, shell < 250 KiB), Lighthouse a11y ≥ 95, and CI. It follows an ADR-documented read-only OT boundary and uses only synthetic data.
- **OTRORA: OT asset inventory & vulnerability management**
  Replaced a legacy desktop (Tkinter) inventory tool with a responsive Next.js 16 + Supabase app, keeping the full data model and workflows. Signup is closed, roles come from `app_metadata`, and RLS is enabled on every table. It uses optimistic concurrency, transactional Excel import with preview, and fails closed when misconfigured. **NVD/CPE-based vulnerability monitoring** runs as a Supabase Edge Function worker and feeds per-asset findings and mitigation planning. The SQL layer is covered by pgTAP tests.
- **Yara: WhatsApp AI agent**
  A TypeScript backend for a Meta WhatsApp Cloud API agent that recommends Buenos Aires events. It uses an Express webhook, Gemini 2.5 Pro for parsing, Drizzle + Postgres, a **pg-boss** job queue, a GCS/Cloud SQL import pipeline, and Vitest + Supertest, with Testcontainers integration tests.
- **Conversational time tracking (client)**
  An iOS-first Expo app where employees log work through a short chat. **Gemini**, running in a Supabase Edge Function, turns the chat into structured draft entries that the user reviews before anything is saved. Per-user and global daily LLM quotas are enforced in Postgres. Tests cover the database (pgTAP) and a live-model corpus.

## Hackathons

- 🥇 **SOLxAR &lt;&gt; Shipyard Hackathon: 1st place (2,500 USDC), Oct 2025.** Argentina track of the Colosseum Cypherpunk global Solana hackathon, run by Superteam. Project: an early version of **Cachin**, a Solana USDC payments app (Expo, Turnkey embedded wallets). · [results](https://superteam.fun/earn/listing/solxar-lessgreater-shipyard-hackathon)
- 🥇 **Midnight Hackathon Buenos Aires: 1st place, Aug 2025** (IOHK / Cardano Foundation). I contributed to the winning project, a privacy-preserving KYC dApp that proves age and country eligibility with zero-knowledge proofs, without revealing the data on-chain. Compact + TypeScript. · [original repo](https://github.com/joacolinares/kyc-midnight) · [my contributions](https://github.com/kevan1/kyc-midnight-hackathon) · [my follow-up](https://github.com/kevan1/midnight-zk-kyc)
- 🏆 **MaskBid: Winner, Transparency category, NMKR Berlin Hackathon, Jul 2024.** A Cardano commit-reveal tender system: companies post RFPs, contractors commit hidden bids, and bids are revealed after the deadline. Aiken, Next.js, TypeScript, Maestro. · [demo](https://private-tender.vercel.app) · [code](https://github.com/MartinSchere/maskbid)
- 🎖️ **Buena Hackday: Honorable mention.**

<sub>Other hackathon builds: [Guards](https://github.com/kevan1/guards-ui) (Pythathon Buenos Aires 2026, Pyth treasury risk engine) · Samurai de Cardano (Cardano Summit 2025, Aiken treasury/crowdfunding validators) · [Neorypto](https://github.com/kevan1/Necrypto-AlephHackathon) (Aleph 2025, Base MiniKit inheritance app) · [Mimic Protocol](https://github.com/kevan1/mimic-hackathon) (2025, on-chain automation) · Cachin at Colosseum Frontier (2026).</sub>

## Background

42 Berlin (software engineering) · IT operations at IRSA · Java/Spring Boot internship at Cresud · DevOps trainee at the Buenos Aires City government (Docker, CI/CD, AWS/GCP, ELK).

## Contact

🌐 [kevan.ar](https://kevan.ar) · ✉️ [git@kevan.ar](mailto:git@kevan.ar) · 𝕏 [@kevan____](https://x.com/kevan____)

<!-- Optional (at most one widget). Uncomment if wanted:
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=kevan1&layout=compact&hide_border=true" alt="Top languages" height="140" />
-->
