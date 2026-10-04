---
name: ndpa-qa
description: "Use this skill when the user asks a question about what the Nigeria Data Protection Act 2023 or the NDPC's GAID 2025 says, means or requires, and wants an answer they can act on, with section citations and a confidence level. Typical questions: whether consent is needed, whether data counts as sensitive, breach notification deadlines, whether an organisation is a data controller of major importance and which tier it falls in, how the GAID relates to the NDPR, and rules on cross-border transfers. The answer comes from reading the law, not from inspecting the user's material. Do NOT use it when the user wants something examined against the law, such as a codebase, school or hospital systems, CCTV setup notes, policies or contracts reviewed for NDPA/NDPC gaps or compliance issues. That is ndpa-audit. Do NOT use it for drafting documents either, which is ndpa-docs. Also not for GDPR or other countries' laws."
---

# NDPA question answering

Answers one question about the Act or the GAID for someone who has to act on it: usually a business owner, school head, IT contractor or their adviser, not a data-protection lawyer. Companion skills: `ndpa-audit` (check a system or document for gaps), `ndpa-docs` (draft the documents). If the user really wants one of those, answer the question briefly and point to the companion.

## Load first
Read `../../references/ndpa-core.md`. Then open the official text in `../../references/source/` (`NDPA-2023.official.txt`, `NDPC-GAID-2025.official.txt`) for every provision the answer turns on and quote the operative words: the core file is a condensed map, and the detail it drops is often the detail that decides the question (provisos, sub-paragraphs, "where…" conditions). Go to the web (https://ndpc.gov.ng/resources/) only for instruments issued after the GAID, or to check that a fee, tier or deadline the answer depends on is still current. One targeted check is enough; say what you checked and what you could not.

## Shape of the answer
Write it so the reader can stop after the first paragraph and still do the right thing.

1. **Bottom line**: one or two sentences that answer the question asked (yes / no / it depends on X), in plain words.
2. **What to do** (when the question is about a real situation): a short numbered list of next steps, most urgent first. If a deadline is involved, work it out against today's date from what the user said ("Friday night" → the actual date and time the clock runs out); if it has probably passed, say so and say what to do now.
3. **Basis**: the provisions, each as `NDPA s.40(2) [Act]` or `GAID Art.33(5) [GAID]`, with a short quote of the operative words. Tag every provision you cite, including ones mentioned in passing, so the reader can tell statute from directive at a glance.
4. **Confidence**, one line: `Text-based` (clear in the Act/GAID), `Interpretive` (open text or conflicting provisions; give the readings), or `Outside the text` (practice, sector rules, case law, how the NDPC enforces; say what to check and with whom). Different parts of an answer can carry different tags.
5. **The deciding fact**, if there is one: end with the one or two questions whose answer would change the conclusion. Answer each branch briefly first, so the answer is usable even if the user never replies.

Add the following only when they change the answer or the reader's next step. Leave them out otherwise; a section that says "no exemption applies" is noise.
- **Act and GAID point different ways** (common for consent: GAID Art.18 against Act ss.30, 37, 41, 43; breach notice to individuals: GAID Art.33(3) against s.40(3)). Give both, say the Act prevails (s.63 [Act]; GAID Art.3(2) [GAID]), and say what the NDPC is likely to expect in practice. Tag `Interpretive`.
- **The GAID is inconsistent with itself** (for example a body that is one tier by named type and another by volume in Sch.7, or Art.10(6) against the Art.9(3) carve-out for the ordinary-high tier). The precedence rule does not settle these. Lead with the reading the text favours (`ndpa-core.md` §2 says which for the tier question), give the other as a risk in one or two sentences, and tag `Interpretive`. Do not turn a reading the text disfavours into the recommended course.
- **Exemption**: where the processing may fall under s.3(2) (law enforcement, public-health emergency, national security, journalism/education/art, legal claims), say what still applies (ss.24, 25, 32, 40, Part VI rights, s.39 security).
- **Role, tier, sector, volume or hosting location** decides it and the user has not said: answer per branch.
- **Exposure**: what the text requires and the penalty range (s.48; s.49 only for ignoring a compliance order). Not a conclusion on liability.
- **Currency**: fees, deadlines, tiers and forms can change by NDPC instrument (GAID Art.50). Say so when the answer depends on one, and that it should be confirmed on ndpc.gov.ng.
- **Standing duties**: when the answer places an organisation in major importance (MI), add one line on what that status brings for its tier: registration or renewal, a DPO (s.32 [Act]), and the annual audit duty (CAR for UHL/EHL; the Art.9(3) [GAID] carve-out and the Art.7(b) [GAID] internal audit for OHL).
- **DPIA**: in a real situation, check the facts against every GAID Art.28(3) trigger, (a) to (o) in `ndpa-core.md`. If any applies, say a DPIA is required before processing and cite each letter that applies.
- **Other law**: when another Nigerian law or regulator obviously bears on the facts (CBN, NCC, health and HIV-status confidentiality, education, NBA rules, Cybercrimes Act), name it as something to check and tag it `Outside the text`. Do not cite its sections from memory or resolve the overlap.

## Length
Match the question. A single-point question ("is religion sensitive data?", "does the GAID replace the NDPR?") deserves a short answer: bottom line, the provision, the tag, roughly 100 to 250 words. A real situation with several branches (a breach, a transfer of sensitive data) can run longer, but every paragraph should change what the reader does or how sure they can be. Do not use headings for sections that have one line of content. Keep a fallback or minority reading to one or two sentences.

## Rules
- Never invent section numbers, penalties or deadlines. If unsure, search the source text; if it is not there, say it is not there.
- Quote provisions for what they actually govern. Check the surrounding paragraph before applying a quote to the user's facts, and use the pinpoint as printed (for example `Sch.7 para 1(1)(c)`).
- Use the Act's own words for its tests ("consent" in s.30(1)(a), "becoming aware" in s.40(2), "immediately" in s.40(3)). GDPR phrasing such as "explicit consent" or "without undue delay" is wrong where the Act says something else.
- The NDPR 2019: do not cite it for current duties. When the question is about the NDPR itself, explain the transition: on issue of the GAID the NDPC ceased to apply it, and things done under it before then are unaffected (GAID Art.3(3) [GAID]; Act s.64(2)(f) [Act], which kept NITDA regulations such as the NDPR in effect until replaced). The GAID was issued on 20 March 2025; the 19 September 2025 effective date comes from an NDPC announcement and is not printed in the GAID, so say which date you mean and where it comes from.
- A fact from the web or a secondary source: name the source, or leave it out. Never state it as if it were in the Act or GAID.
- Quotation marks mean verbatim: copy the words from the source file exactly. If you paraphrase, drop the quotation marks.
- When you set out alternative risks or readings, keep each consequence with its own trigger ("if over 1,000 data subjects → EHL"; "if Art.10(6) is read literally → an OHL school files a CAR"). Do not merge them into one conclusion.
- Do not say the NDPR (or any earlier regime) lacked something unless you have checked; say what is "new or changed" instead.
- Every factual claim from outside the Act and GAID (how ransomware groups behave, enforcement practice, sector rules) carries `Outside the text`, and every provision you mention, including a second mention, carries its [Act] or [GAID] tag.
- Keep Act, GAID and sector rules separate. But when another law directly governs the data in question (HIV status confidentiality, banking secrecy), mention it in the bottom line as a possible second barrier, not only as a closing note.
- Sensitive data: walk the s.30(1) grounds (read the full paragraph in the source; several have a second limb), then GAID Art.18(1)(b). Transfers abroad: s.41(1)(a), then s.43, then the s.41(2) record, then GAID Art.18(1)(e).
- This is a compliance aid, not legal advice. Say so once, briefly, where the stakes are real; do not pad every answer with disclaimers.

## Before you finish
Check the draft against this list; each item is a rule above that is easy to drop.
- The first paragraph answers the question on its own.
- Every provision mentioned carries [Act] or [GAID]; anything else carries `Outside the text`; the confidence tag is there.
- If the answer makes the organisation MI: the standing-duties line is there.
- If it is a real situation: the Art.28(3) triggers were checked, and each one that applies is cited.
- Any fee, tier or deadline relied on is flagged as changeable (Art.50 [GAID]) and to be confirmed on ndpc.gov.ng.
