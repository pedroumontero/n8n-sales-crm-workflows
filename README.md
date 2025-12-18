# n8n Sales & CRM Automation Workflows

Production-ready **n8n workflows** for automating sales and CRM operations at scale.

This repository focuses on **real-world automation patterns**, not toy examples.
Designed for teams that need **data integrity, ownership rules, traceability, and scalability**.

---

## 🎯 What this repository is

A practical collection of **workflow blueprints** used to automate the full sales lifecycle:

**Lead Capture → Normalization → Deduplication → Routing → CRM Sync → Reporting**

Built with a **database-first mindset**, where automation enforces business rules — not the other way around.

---

## 🧠 Core automation principles

- Database-first logic (MySQL as source of truth)
- Deterministic deduplication (not fuzzy guesses)
- Explicit ownership & routing rules
- Full traceability (source, consent, timestamps)
- Idempotent workflows (safe replays)
- Separation of concerns (capture ≠ logic ≠ CRM)

---

## 🧩 Workflow architecture (E2E)

```text
[Forms / Landing Pages / APIs]
              ↓
         n8n Webhook
              ↓
      Input Validation Layer
              ↓
   Data Normalization (phone, name, source)
              ↓
   Deduplication Logic (MySQL)
              ↓
 Business Rules Engine
 (routing, ownership, SLAs)
              ↓
        CRM Sync (Perfex)
              ↓
      Notifications & KPIs
⚠️ Some workflows are reference implementations / sanitized examples.
Sensitive business logic and credentials are intentionally excluded.

🔄 Key workflows explained
1️⃣ Lead Intake (Webhook)

Accepts leads from forms, landing pages, CSV uploads, APIs

Captures:

Phone

Name

Source

Consent

Metadata (campaign, referrer, timestamps)

2️⃣ Data Normalization

Phone normalization (E.164 / last 10 digits)

Name cleanup & casing

Source standardization

Consent validation

3️⃣ Deduplication (Database-first)

No CRM-side guessing

Uses MySQL unique logic

Prevents:

Duplicate leads

Ownership overrides

KPI corruption

4️⃣ Routing & Ownership

Assignment by:

Team

Territory

Campaign

Availability

SLA-aware logic

No “round-robin magic”

5️⃣ CRM Sync (Perfex)

Create or update leads safely

Custom fields mapping

Ownership enforcement

Audit-friendly updates

6️⃣ Notifications & KPIs

WhatsApp / Email / Internal alerts

Real-time dashboards

Funnel visibility

🛠 Tech stack

n8n — workflow orchestration

MySQL — validation, dedupe, integrity

Perfex CRM — lead & sales management

Webhooks / APIs — ingestion layer

🚫 What this repo is NOT

❌ No “connect Zapier and pray”

❌ No CRM-as-database anti-patterns

❌ No manual Excel-based routing

❌ No black-box automations

👤 Author

Pedro Urribarri
Automation & AI Engineer — Sales & CRM Systems

I design and build end-to-end automation systems that replace manual operations with structured, scalable workflows.

📌 Notes

This repository evolves as systems grow.
Expect updates around:

Error handling patterns

High-volume scaling

Multi-CRM architectures

AI-assisted enrichment (future)
