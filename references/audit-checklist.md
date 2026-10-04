# NDPA audit checklist — control tests with evidence sources (v0.2.0, 42 controls)

Each row: control ID · what to test · where evidence usually lives · basis. Basis tags: [Act], [GAID], [practice] (good practice or inference — never report a [practice] control as a legal breach). See `ndpa-core.md` §0 for precedence.

Statuses:
- **PASS / PARTIAL / FAIL** — tested against evidence. Use FAIL for something required at go-live that is absent, even if not built yet; say "(not yet built)".
- **NOT EVIDENCED** — the evidence would live somewhere you did not examine (another system, the client's files). A governance document missing from a code repo is NOT EVIDENCED unless the client confirms it does not exist.
- **N/A** — the activity genuinely does not occur in scope (e.g. no direct marketing). "Not built yet" is not N/A.
- **Which wins:** "FAIL (not yet built)" applies to features of the system under test. A document owned by someone else (the controller's DPIA, breach plan, contracts) stays NOT EVIDENCED until its owner confirms it does not exist; record who confirmed it.

## A. Governance
| ID | Test | Evidence | Basis |
|---|---|---|---|
| G1 | MI status determined and recorded (tier, reason, including the commercial-ICT-services gate) | registration cert, NDPC portal receipt, internal memo | [Act] s.44, s.65; [GAID] Art.8–9, Sch.7 |
| G2 | Registered on becoming MI (OHL renewed annually); changes notified within 60 days | NDPC registration proof | [Act] s.44(1),(3); [GAID] Art.9 |
| G3 | DPO designated (MI controllers; MI processors too under GAID), contact published and sent to NDPC, reports to management | org chart, website, appointment letter | [Act] s.32; [GAID] Art.7(i), 11–12 |
| G4 | Semi-annual DPO report exists and is in RoPA | last two reports | [GAID] Art.13 |
| G5 | Compliance audit within 15 months of starting, then annually; UHL/EHL audit return filed by 31 March via DPCO | audit report, CAR receipt | [GAID] Art.7(b)-(c), 10 |
| G6 | Record of processing activities (RoPA) current | RoPA doc | [GAID] expected by Art.13(2)–(3), Sch.1 para 1(iii) (no express duty) |
| G7 | Staff training within 6 months of start and annually; schedule published | training log, schedule | [GAID] Art.7(v), 30, 46 |
| G8 | Internal privacy policy, staff checklist, retention policy | policy docs | [GAID] Art.7(n), 30(7), Sch.1 para 4 |

## B. Lawfulness and transparency
| ID | Test | Evidence | Basis |
|---|---|---|---|
| L1 | Every processing purpose has a documented lawful basis (and, for law firms, which activities rely on the s.3(2)(e) legal-claims exemption) | RoPA, policy | [Act] s.25, s.3(2); [GAID] Art.16 |
| L2 | Consent captured where relied on **and** in each GAID Art.18 case (direct marketing, sensitive data, incompatible further processing, children, transfer without NDPC adequacy decision, solely automated decisions): affirmative, specific, not pre-ticked, recorded and retrievable | consent tables, form code, UI | [Act] s.26; [GAID] Art.17–18 (Art.18 vs Act grounds is Interpretive) |
| L3 | Withdrawal as easy as giving consent; refusal not detrimental | UI, API, ops runbook | [Act] s.35; [GAID] Art.17(7). Propagation to processors: [practice] |
| L4 | Legitimate interest has an LIA done before processing | LIA doc (Sch.8) | [Act] s.25(2); [GAID] Art.26 |
| L5 | Privacy policy published, covers s.27(1)(a)–(g) and GAID Art.27(3) items, readable for the audience, includes retention | website/app/policy | [Act] s.27; [GAID] Art.7(j)-(m), 27; Sch.1 para 4(vii) |
| L6 | Cookie/tracker banner seen without scrolling and significantly obstructing the middle, left or right of the home page (bottom banner fails); accept/reject; no non-necessary trackers before consent (necessary = security, network stability, accessibility, and not sensitive/financial data) | site, network trace, tag manager | [GAID] Art.19, 7(l) |
| L7 | Sensitive data only under a s.30 ground (note (e) legal claims/legal advice/proceedings) and GAID Art.18(1)(b) consent where feasible | schema, forms, documents, policy | [Act] s.30, s.65; [GAID] Art.18 |
| L8 | Children's data: where consent is relied on, parental consent and age/consent verification; s.31(4) exceptions documented | signup flow, school forms | [Act] s.31; [GAID] Art.18(1)(d) |

## C. Minimisation, retention, accuracy
| ID | Test | Evidence | Basis |
|---|---|---|---|
| M1 | Fields collected are necessary for stated purpose | schema, forms | s.24(1)(c) |
| M2 | Retention period defined per dataset and enforced (job/script/process); default ≤6 months after purpose ends if no law fixes one; legal-claims hold allowed | retention schedule, cron/TTL, backups policy | [Act] s.24(1)(d); [GAID] Art.49(3)-(4), Art.21(2), Sch.1 para 4 |
| M3 | Data can be corrected; no charge for the controller's own errors | UI/API | [Act] s.34(1)(c); [GAID] Art.36 |
| M4 | Test/dev environments do not hold live personal data unprotected | env configs | [Act] s.24, 39 |

## D. Security
| ID | Test | Evidence | Basis |
|---|---|---|---|
| S1 | Encryption in transit (TLS config) and at rest for personal/sensitive data | server/DB config, cloud settings | [Act] s.39(2)(b) |
| S2 | Passwords hashed with a modern KDF; secrets not in code/repo | code, repo scan | [Act] s.39(1) |
| S3 | Role-based access, least privilege, MFA on admin/remote access | IAM, AD/M365 config | [Act] s.39(1) (GAID Art.29(2)(f) only lists "authentication checks" in the maintenance schedule) |
| S4 | Access/audit logging for personal data | log config | [practice] — supports s.24(3) accountability and s.40(8) breach records |
| S5 | Backups, restore tested, offsite/immutable | backup report | [Act] s.39(2)(d) |
| S6 | Patching and vulnerability testing on a written schedule vetted by a certified infosec officer | schedule, scan reports | [Act] s.39(2)(e)–(g); [GAID] Art.29 |
| S7 | Endpoint/server/deployment hardening; no exposed data stores or default credentials; remote access protected | configs, manifests | [Act] s.39(1) |
| S8 | Physical security of server rooms, NVRs, paper files | site check | [Act] s.39(1) |

## E. Rights handling
| ID | Test | Evidence | Basis |
|---|---|---|---|
| R1 | Intake channel for access/rectify/erase/restrict/object/portability requests; tracked; answered without constraint or unreasonable delay | form, mailbox, log | [Act] ss.34–38; [GAID] Art.7(s)–(u) |
| R2 | System can locate, export (common electronic / machine-readable format) and erase one person's data, with documented exceptions (legal claims, legal obligation) and third-party erasure | code/endpoints, runbook | [Act] s.34; [GAID] Art.37–38 |
| R3 | Direct-marketing opt-out honoured | mailing tool config | [Act] s.36(3)–(4) |
| R4 | Automated decisions with significant effect have human review and contest path | process doc | [Act] s.37 |
| R5 | Complaints process explained incl. right to complain to NDPC; SNAG notices answered (Sch.9 form asks for the stated time or 30 days, whichever is earlier) and decision reported to the NDPC platform | policy, log | [Act] s.27(1)(f); [GAID] Art.7(w), 39, 40, Sch.9 |

## F. Third parties and transfers
| ID | Test | Evidence | Basis |
|---|---|---|---|
| T1 | Written agreement with every processor/sub-processor containing Art.34(2) items | contracts | [Act] s.29(2); [GAID] Art.34 |
| T2 | Processor's compliance checked, incl. NDPC registration where MI | register check | [GAID] Art.34(2)(m),(3) |
| T3 | Inventory of where data is hosted/sent (cloud region, SaaS, analytics SDKs, email, calendars, backups, AI hosts) | architecture, DNS, network calls, vendor list | [practice] — prerequisite for s.41(2) |
| T4 | Transfer basis + adequacy assessment recorded for each foreign destination; GAID Art.18(1)(e) consent position stated | transfer register | [Act] s.41(2), 42, 43; [GAID] Art.18(1)(e), Sch.5 |

## G. Incidents
| ID | Test | Evidence | Basis |
|---|---|---|---|
| I1 | Breach response plan: 72-hour NDPC notification, immediate subject notice for high risk, Art.33(5) content, owner named | IR plan | [Act] s.40; [GAID] Art.33 |
| I2 | Breach record kept | register | [Act] s.40(8) |
| I3 | Processor-to-controller breach notification duty in contracts | DPA | [Act] s.40(1) |

## H. DPIA
| ID | Test | Evidence | Basis |
|---|---|---|---|
| D1 | DPIA exists and is filed with the NDPC for every GAID Art.28(3) trigger (a)-(o): profiling, automated decisions, monitoring, sensitive data, vulnerable subjects, new technology, software for communicating with data subjects, digital financial services, health, e-commerce, public-area cameras, public-data legal instruments, education records, hospitality, cross-border transfer; note any s.3(2) exemption claimed | DPIA docs, NDPC receipt | [Act] s.28; [GAID] Art.28(3),(8)-(10) |
| D2 | DPIA has s.28(4) content, Sch.4 structure, privacy-by-design measures, signed by accredited DPO, done before processing | DPIA doc | [Act] s.28(4); [GAID] Art.28(9),(11)–(13) |

## Technology-specific probes
**Source code / repo**: grep schema and models for name, phone, email, address, DOB, NIN, BVN, voter/passport/driver numbers, photos, face/biometric templates, health fields, religion/ethnicity, location, IP, device IDs; find consent fields and cookie code; third-party SDKs (analytics, ads, crash reporting, maps, payment); outbound hosts; personal or sensitive data carried in URLs or query strings; logging of personal data; delete/export endpoints; admin panels; seed/test data with real records.
**CCTV / access control / NVR**: purpose and lawful basis; DPIA (public-area cameras are a mandatory trigger, GAID Art.28(3)(k)); "intrusive use of CCTV" is a listed SNAG grievance (Sch.9); signage; retention setting vs policy; who can view/export; default credentials; firmware patched; remote viewing exposure; audio recording (extra intrusion); biometric access control (sensitive data, s.30); processor agreement between installer/operator and owner.
**Servers / M365 / AD**: MFA, conditional access, admin separation, mailbox sharing, retention labels, DLP, backup, offboarding, USB/laptop encryption, shared drives with open permissions.
**Documents/policies only**: map every s.27(1) item and every GAID Art.34(2) item to a clause; list missing and vague ones.

**Deployment manifests (compose, Helm, Terraform, env files)**: published ports for databases, object stores and admin UIs; default or fallback credentials (`${VAR:-default}`); least-privilege DB login; TLS mode enforced or merely preferred; production-guard validator covers each of these; secrets in repo or image; volumes holding documents unencrypted; backups and restore tested.
**Access-control granularity (any multi-user system)**: authorisation map of every route; roles seeded and enforced; record-level checks (matter team, branch, ethical walls) in the service layer; calendar/feeds scoped per user; token-in-URL features (expiry, revocation, who else fetches them).
**Legal-practice systems**: which processing relies on the s.3(2)(e) legal-claims exemption and s.30(1)(e) (legal claims, legal advice, proceedings) and which does not (billing, HR, portal, marketing); privilege and confidentiality (matter-level access, walls), client-visible documents default hidden, trust-account records and retention duties (state the period and its source; VERIFY with the firm), adverse parties and opposing counsel as data subjects in conflict checks, court filings with sensitive categories.
**AI / MCP integrations**: GAID Art.43 parameters and DPIA (disparate outcomes, Sch.6 vulnerability indexes); which hosts receive data and where they are located (s.41-43, GAID Art.18(1)(e)), per-firm allow-list, minimisation list, audit of tool calls, no AI path to deletion or money movement, untrusted-content handling.
**Logging**: grep log calls for raw exception messages, request bodies, file paths and identifiers.
