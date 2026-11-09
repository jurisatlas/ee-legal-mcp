---
name: ee-legal-mcp-skill
description: Official Estonia (EE) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Estonia Legal Research & Multi-Tier Case Law Skill (`ee-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Estonia (EE)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:EE:RK:2024:1.23.4567 or RT I, 01.01.2024, 1`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** 4 Maakohtud (Harju, Tartu, Viru, Pärnu County Courts) & 2 Halduskohtud (Tallinn & Tartu Administrative Courts)
   - **Second Instance (Cantonal / Regional / Appellate):** 2 Ringkonnakohtud (Tallinna Ringkonnakohus & Tartu Ringkonnakohus — Circuit Courts of Appeal)
   - **Supreme & Constitutional Instance:** Riigikohus (Supreme Court of Estonia — Civil, Criminal, Administrative & Constitutional Review Chambers)
   - **Primary Tiered Database:** Riigi Teataja Kohtulahendid (riigiteataja.ee — All County, Administrative, Circuit & Supreme Court Judgments) (`https://www.riigiteataja.ee/kohtulahendid/`)
