---
name: ndpa-docs
description: Draft NDPA 2023 / NDPC GAID 2025 compliance documents for a client - privacy notice, cookie notice, consent forms, DPIA, data processing agreement, legitimate interest assessment, breach response plan and register, RoPA, retention schedule, data subject request and SNAG procedure, transfer register, CCTV signage notice, software pre-install privacy statement, DPO semi-annual report. Use when asked to write or fix a data-protection document.
---

# NDPA document generator

## Load first
`../../references/ndpa-core.md`. Then the provisions for the document you are drafting (the Basis column below). For template-driven documents, read the template in `../../references/source/NDPC-GAID-2025.official.txt`: **Schedule 4** (DPIA), **Schedule 8** (LIA), **Schedule 9** (SNAG), **Schedule 2** (audit-return questions, useful as a self-check). If an `ndpa-audit` report exists for this client, build from its data map and findings instead of re-asking.

## Inputs to collect (ask once, only what is missing)
Client legal name and address; role (controller/processor); MI tier; what personal data, whose (customers, staff, pupils, patients, visitors, adverse parties), why, which systems; processors and their locations; retention; DPO name and contact; website/app URLs; any s.3(2) exemption relied on. Use `[PLACEHOLDER: what is needed]` for anything still unknown. Never invent registration numbers, dates, names or facts.

## Document specs
| Document | Must contain | Basis |
|---|---|---|
| **Privacy notice/policy** | controller identity and contact; lawful basis per purpose; purposes; types of data; means of processing; recipients and third-party access with purpose; rights (access, rectify, erase, restrict, object, withdraw consent, portability, automated-decision safeguards); retention periods and what that means for access requests; internal remediation contact and DPO; right to complain to the NDPC; automated decisions/profiling; plain language for the audience | [Act] s.27; [GAID] Art.7(j)-(m), 27, Sch.1 para 4(vii) |
| **Cookie notice + banner spec** | banner seen without scrolling, significantly obstructing the middle, left or right of the home page (not a bottom bar); accept/reject; categories and purpose; responsible organisation; how to withdraw; necessary cookies defined per Art.19(6) and excluding sensitive/financial data (flag basket, login and payment-gateway cookies as judgement calls); no non-necessary trackers before consent; closing the banner without choosing is implied consent to basic functionality only (Art.17(8)(b)), so treat it as reject | [GAID] Art.19, 7(l) |
| **Consent form / consent record spec** | separate request per Art.18 case (direct marketing, sensitive data, incompatible further processing, children, transfer without NDPC adequacy decision, solely automated decisions); affirmative, not pre-ticked; right to withdraw stated first; refusal without detriment; record who, what, when, version | [Act] s.26, 35; [GAID] Art.17-18 |
| **DPIA** | follow Sch.4 sections: general background; nature of processing; lawful basis and context; necessity and proportionality; stakeholder consultation; vulnerabilities (incl. Sch.6 indexes); likelihood and severity; disparate outcomes; cross-border transfer; principles and rights; mitigation; final assessment. Check the facts against every Art.28(3) trigger, (a) to (o) in `ndpa-core.md`, and cite each letter that applies (cameras in places the public can enter are (k); children are (e) vulnerable data subjects); include privacy by design/default; sign-off block for an NDPC-accredited DPO; NDPC consultation decision for residual high risk | [Act] s.28; [GAID] Art.28, 43(4), Sch.4, Sch.6 |
| **Data processing agreement** | GAID Art.34(2)(a)-(t); s.29(1) processor duties (follow the Act, assist with rights, secure data, provide compliance information, notify sub-processors); s.40(1) breach notice to controller; erasure/return at end; audit rights | [Act] s.29, 40(1); [GAID] Art.34 |
| **Legitimate interest assessment** | Sch.8 parts: purpose test, necessity test, balancing test (nature of data, reasonable expectations, likely impact, opt-out), decision, sign-off | [Act] s.25(2); [GAID] Art.26, Sch.8 |
| **Breach response plan + notices + register** | detection and triage; risk decision; NDPC notice within 72 hours with Art.33(5)(a)-(h); immediate data-subject notice for high risk in plain language with mitigation advice (or public notice); processor-to-controller duty; phased reporting; breach register (facts, effects, remedial action); contact point | [Act] s.40; [GAID] Art.33 |
| **RoPA** | per activity: purpose, data categories, subjects, lawful basis (or exemption), recipients, transfers and basis, retention, security measures, DPIA reference | [GAID] Art.13, Sch.1 para 1(iii) |
| **Retention schedule** | dataset, purpose, period and its legal source (VERIFY sector or professional rules), trigger, deletion or de-identification method, legal-claims hold; default 6 months after purpose ends where no law fixes a period; 6-month destruction where a contract did not materialise | [Act] s.24(1)(d); [GAID] Art.49, 21(2), Sch.1 para 4 |
| **Data subject request + SNAG procedure** | intake channels, identity check, owner, response without constraint or unreasonable delay, per-right steps and exceptions (legal claims, legal obligation), third-party erasure, record of refusals; SNAG: decision within the time stated or 30 days, whichever is earlier, report the decision to the NDPC platform; reply template | [Act] ss.34-38; [GAID] Art.36-40, Sch.9 |
| **Cross-border transfer register** | destination, recipient, data, basis (s.41(1)(a) instrument or s.43 ground), adequacy assessment on s.42(2) factors, GAID Art.18(1)(e) consent position, date, review date | [Act] s.41(2), 42, 43; [GAID] Art.45, Sch.5 |
| **CCTV signage and notice** | who operates the cameras and contact; purpose and lawful basis; retention; where the full privacy notice is; DPIA reference for public-area cameras | [Act] s.27; [GAID] Art.27(2), 28(3)(k) |
| **Software pre-install privacy statement** | Art.31(2)(e)(i)-(ix) items: data types, lawful purpose, minimisation, technical measures (name them), DPIA result, support link, disable/uninstall link, complaint route with authorities | [GAID] Art.31 |
| **DPO semi-annual report** | items (a)-(m) of Art.13(5) | [GAID] Art.13 |

## Who reads what
Each document has a working reader (the shopper, the school bursar, the law-firm partner signing) and a reviewer (the DPO or lawyer who checks it). Write for both without making either wade through the other's material:
- **Public-facing documents** (privacy notice, cookie notice and banner text, CCTV sign, pre-install statement): the main text must be ready to publish once placeholders are filled: plain prose, no basis column, no clause tables, no [ASSUMPTION] or [VERIFY] markers inside the text the public will read. Put the provision-by-provision citations, assumptions and open items in a **Reviewer notes** annex at the end (or a second file), keyed to section numbers, with a note to delete it before publishing.
- **Contracts** (DPA): the agreement itself reads as a normal contract, with citations, if any, in footnotes. The Art.34(2) checklist mapping each item to a clause, the assumptions and the lawyer-review list go in a removable **Reviewer schedule** marked "remove before signing".
- **Internal documents** (DPIA, LIA, RoPA, retention schedule, breach plan, registers): the provision goes next to each section (margin column or footnote), tagged [Act] or [GAID].
- Public text must not assert facts only the client can confirm ("we have checked this does not override your rights", "staff are trained", "records are kept securely"). Make each a placeholder or list it in the reviewer notes as a commitment to confirm. Say in the reviewer schedule whether contract footnotes are to be kept or stripped before signing.
- A DPIA starts with a one-page decision summary (outcome, conditions, who must act) before the Sch.4 sections.
- Open every document with three or four plain sentences for the client: what this document is for, who must do what before it is used, and the most important open item.

## Output rules
- Read the matching file-format skill before building: docx skill for policies, contracts, DPIAs; xlsx skill for RoPA, retention schedule, registers. If the user did not specify, use .docx for narrative documents and .xlsx for registers. If no such skill is available, build the file with whatever tool you have (python-docx, openpyxl, pandoc). A Markdown file on its own does not meet this; keep one only as an extra copy.
- Save to the user's output folder (or where the user names), named `<client>-<document>-<YYYY-MM-DD>` with today's date (use a short descriptive name such as `online-shop` when the client is unnamed); never into this plugin's folder. If you rebuild a document, overwrite or delete the earlier file so only the current version is left.
- Start each document with: "Prepared against NDPA 2023 and NDPC GAID 2025; review by a qualified Nigerian data-protection professional before issue."
- Placeholders: `[PLACEHOLDER: what is needed]` for anything unknown. A guessed number in brackets ("[600] pupils") is still an invented fact; use a placeholder. For inventories you do not have (cameras, systems, processors), give two or three example rows and "repeat for each", not one empty row per item. In the opening, say how many placeholders there are and which five matter most.
- Citations: before saving, find each cited article or sub-paragraph in the source text and check that its words support the clause it is attached to. Cite the provision that actually says it (for example, access is Act s.34(1)(a), not GAID Art.36, which is rectification).
- Contracts: plain English; flag clauses needing a lawyer (indemnity, liability caps, governing law, privilege for law-firm clients).
- Cloud providers in a DPA (Microsoft 365, Google Workspace, AWS): state their role. If the client contracts with the cloud provider directly, it is the client's processor; if the service provider resells the subscription (e.g. Microsoft CSP), it may be the service provider's sub-processor, although CSP customers usually also accept Microsoft's customer agreement directly (VERIFY per contract). When unknown, draft both options. Either way, state where the data sits and the transfer basis (s.41-43).
- Never present a DPIA as signed or filed; accredited-DPO sign-off and NDPC filing are for the client.
- After building, give the user a short reply: what was produced, where it is saved, the top open items, and anything launch-critical you noticed outside the request (for example a mandatory DPIA or registration).

## Before you finish
Check the file against this list; each item is a rule above that is easy to drop.
- The format is .docx (narrative) or .xlsx (registers), saved in the output folder the user or the task names, with the `<client>-<document>-<YYYY-MM-DD>` name. Not in the working folder's root, and not in this plugin.
- The very first line of the document is the "Prepared against NDPA 2023 and NDPC GAID 2025…" sentence, then the plain opening for the client.
- Unknown facts are `[PLACEHOLDER: …]`; the opening gives the count and the five that matter most.
- Internal documents carry an [Act] or [GAID] tag beside each section; public documents and contracts keep citations in the reviewer annex or schedule.
- For a DPIA, or anything that needs one: every applicable Art.28(3) letter is cited, and the DPIA is not presented as signed or filed.
- Every citation was checked against the source text.
