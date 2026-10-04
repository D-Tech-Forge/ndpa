# NDPA compliance skills for Claude

Help with Nigeria's data protection law, the **Nigeria Data Protection Act 2023 (NDPA)** and the Nigeria Data Protection Commission's **General Application and Implementation Directive 2025 (GAID)**. Built for business owners, school and clinic managers, IT contractors and their advisers who need to act on the law, not just read it.

Every answer cites the section or article it relies on, says whether that comes from the Act or the GAID, and gives a confidence level. The full official text of the Act and the GAID ships with the plugin, so citations are checked against the source rather than memory.

## Skills

| Skill | Use it when you want to… | You get |
|---|---|---|
| `ndpa-qa` | ask what the law says or requires: registration and tiers, consent, sensitive data, breach deadlines, transfers abroad, whether the NDPR still applies | a short answer you can act on, with the provisions behind it |
| `ndpa-audit` | check something concrete against the law: an app or codebase, a server or CCTV setup, a privacy policy, contracts | a gap report with findings ranked by severity, the basis for each, and what to fix first |
| `ndpa-docs` | draft a compliance document: privacy notice, cookie banner spec, consent forms, DPIA, data processing agreement, breach plan, RoPA, retention schedule and more | a Word or Excel draft with placeholders for facts only you can supply, and reviewer notes |

Claude picks the right skill from your request. For example:
- "Do we have to register with the NDPC? We're a secondary school in Lagos with 600 pupils."
- "Check this booking app against the NDPA before we go live."
- "Draft a DPIA for our school's CCTV system."

## What the plugin does with your data

- It runs inside your Claude session. It has no server and sends nothing to The Tech Forge.
- It reads only the files you point it at, and writes reports and drafts to the folder you name.
- To confirm that a fee, deadline or tier is still current, it may look up pages on the NDPC website (ndpc.gov.ng). It says what it checked.
- Audit reports name the systems examined and their weaknesses. Keep them somewhere appropriate for confidential client material.

## Limits

This is a compliance aid, not legal advice. The legal content has been checked against the official text of the Act and the GAID, but not yet by a Nigerian data-protection lawyer. Have a qualified data-protection professional review anything you rely on or file. NDPC fees, tiers and forms can change (GAID Art.50), so confirm current requirements on ndpc.gov.ng.

## About

Made by Abdul Adelubi at The Tech Forge (dtechforge.com). Questions, corrections and feedback: info@dtechforge.com.

© 2026 The Tech Forge. See `LICENSE`.
