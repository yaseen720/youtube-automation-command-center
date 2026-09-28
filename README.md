<div align="center">
  <img src="assets/studioos-logo.png" alt="StudioOS Logo" width="120" onerror="this.style.display='none'"/>
  <h1>🎬 YouTube Automation Command Center (StudioOS)</h1>
  <p><strong>Enterprise Production Management, AI Workflows & Financial OS for Multi-Channel Media Houses</strong></p>

  <p>
    <a href="https://youtube-automation-command-center-beige.vercel.app/"><img src="https://img.shields.io/badge/Live_Demo-Vercel-black?style=for-the-badge&logo=vercel" alt="Live Demo" /></a>
    <img src="https://img.shields.io/badge/Status-Production_Ready-brightgreen?style=for-the-badge" alt="Production Ready" />
    <img src="https://img.shields.io/badge/Architecture-Cloud_Native-blue?style=for-the-badge" alt="Cloud Native" />
  </p>

  <p>
    <a href="#-system-architecture">Architecture</a> •
    <a href="#-key-capabilities">Key Features</a> •
    <a href="#-ui-walkthrough">UI Walkthrough</a> •
    <a href="#-technical-stack">Tech Stack</a> •
    <a href="#-security--access-control">Security</a> •
    <a href="#-live-access--demonstrations">Live Demo</a>
  </p>
</div>

---

> [!NOTE]
> **Commercial Product Notice**: This repository contains the public architecture documentation, UI demonstrations, and product case study for the **YouTube Automation Command Center**. The core codebase and proprietary algorithms are maintained in a private commercial repository.

---

## 💡 Overview & Business Impact

Operating automated and faceless YouTube channels at scale introduces major friction points: disjointed communication across WhatsApp, untracked editor hours, delayed thumbnail revisions, disconnected YouTube analytics, and unorganized freelancer payouts.

**StudioOS** resolves this by consolidating the entire channel lifecycle into a unified operating system:
* **Production Pipeline**: End-to-end task tracking from script drafting, voiceover, and editing to thumbnail approvals.
* **YouTube Data API Sync**: Automated real-time tracking of subscriber milestones, views, and revenue per channel.
* **Financial Ledger & AI Accounting**: Double-entry bookkeeping tailored for digital studios with profit-share calculation and expense tracking.
* **WhatsApp Cloud Integration**: Automated task briefings, deadline reminders, and payout alerts delivered directly to staff phones via Meta Cloud API.
* **Multi-Platform Ecosystem**: Web Command Center paired with an Android Companion App (`StudioOS APK`) and a background Desktop Activity Agent.

---

## 🏗️ System Architecture

```mermaid
flowchart TD
    subgraph ClientLayer ["Client Layer"]
        Web["Web Command Center<br/>(React 19 + Vite + Tailwind v4)"]
        Mobile["Companion Mobile App<br/>(React Native / Expo)"]
        Desktop["Desktop Activity Agent<br/>(Screen & Attendance Monitor)"]
    end

    subgraph ApiGateway ["API & Business Services"]
        Express["Express.js Server Engine<br/>(TypeScript + REST API)"]
        Auth["Firebase Auth<br/>(Google OAuth 2.0 + RBAC)"]
    end

    subgraph ExternalApis ["External AI & Cloud Integrations"]
        Gemini["Google Gemini AI API<br/>(Content Planning & Accounting AI)"]
        YT["YouTube Data API v3<br/>(Channel Sync & Video Metrics)"]
        Meta["Meta WhatsApp Cloud API<br/>(Automated Team Dispatch)"]
    end

    subgraph DataLayer ["Persistence & Storage"]
        Firestore[("Firebase Firestore<br/>Multi-Tenant NoSQL")]
        Storage[("Firebase Storage<br/>Assets, Briefings, Screenshots")]
    end

    Web <--> Express
    Mobile <--> Express
    Desktop <--> Express

    Express <--> Auth
    Express <--> Gemini
    Express <--> YT
    Express <--> Meta

    Express <--> Firestore
    Express <--> Storage
