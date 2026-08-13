# CorezAI — Voice Agent Analytics Dashboard

> Full-stack analytics dashboard for an AI voice receptionist platform serving Australian healthcare practices.

![Next.js](https://img.shields.io/badge/Next.js-14-black?style=flat-square&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=flat-square&logo=typescript)
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?style=flat-square&logo=postgresql)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-38B2AC?style=flat-square&logo=tailwind-css)

## Overview

CorezAI is a production SaaS dashboard that gives healthcare practice managers full visibility into their AI voice receptionist's activity — every call, transcript, recording, appointment outcome, and billing minute in one place.

## Features

- **Overview Tab** — live stat cards (total calls, avg duration, resolution rate) with one-click date filters
- **Insights Tab** — actionable patient outcome tracking: new patients registered, appointments booked, cancelled, rescheduled, and transferred calls — each section paginated independently
- **Calls Tab** — paginated call list with phone number search, date range filters, and a priority-based action column with professional display names
- **Transcripts Tab** — full-text transcript search with live debounced input, two-sided chat bubble UI (agent left, caller right) with automatic speaker detection
- **Recordings Tab** — custom dark-themed audio player built in React, consistent across all browsers and operating systems
- **Billing Module** — real-time minutes usage calculated directly from call duration data, with automatic billing period rollover
- **Security** — full multi-tenant isolation, every query scoped to the authenticated session's clientId, auth guard on all API routes

## Screenshots

### Login
![Login](login%20page.png)

### Overview
![Overview](overview.png)

### Insights
![Insights](Insight.png)

### Calls
![Calls](Call.png)

### Transcripts
![Transcripts](Transcript.png)

### Recordings
![Recordings](Recording.png)

### Call Detail
![Call Detail](Call%20Detail.png)

## Tech Stack

| Technology | Purpose |
|-----------|---------|
| Next.js 14 (App Router) | Framework, server components, API routes |
| TypeScript | End-to-end type safety |
| React 18 | Component architecture, custom hooks |
| Prisma ORM | Type-safe database access |
| PostgreSQL | Primary database |
| NextAuth.js | Session-based authentication |
| Tailwind CSS | Utility-first styling |
| Twilio | Call recording proxy |

## Key Implementation Details

- **Timezone-correct filtering** — all date logic uses Brisbane (UTC+10) with independent from/to bounds
- **Priority action system** — parses comma-separated AI agent action logs into highest-priority single outcome (NewPatientCreated > BookedAppointment > CancelledAppointment etc.)
- **Custom audio player** — built from scratch in React with no native browser controls, eliminating cross-browser rendering inconsistencies
- **Automatic speaker detection** — transcript parser scans raw text to identify agent name and renders two-sided chat UI dynamically
- **Multi-tenant security** — clientId scoping enforced on every Prisma query, URL parameter ownership verified on all dynamic routes, silent redirect on unauthorized access

## Role & Contribution

Built as technical lead and product owner — responsible for full-stack architecture, feature design, implementation direction, security audit, and deployment coordination across a two-developer team.

---

*Note: This is a portfolio documentation repository. The production codebase is maintained privately.*
