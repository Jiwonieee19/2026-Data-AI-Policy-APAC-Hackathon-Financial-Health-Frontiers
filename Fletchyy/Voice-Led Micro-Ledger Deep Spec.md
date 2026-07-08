---
type: Tweak Plan
status: Draft
priority: High
based-on: Idea 2 - Voice-Led Ledger for Micro-Merchants
depth-target: Alagad-level (IDEA 1 in Ryy Understanding)
created: 2026-07-08
---

# Voice-Led Micro-Ledger — Deep Spec Plan

## The Core Pivot

**Before (original):** Voice note → ledger → merchant gets insights → FSP sees cleaner data
**After (tweaked):** Voice note → ledger → **AI detects cashflow anomalies** → FSP gets **automated distress signals + intervention recommendations** for portfolio

Same input channel. Different output beneficiary. The FSP is the customer, not the merchant.

---

## What's Missing vs. Alagad-Level Depth

### 1. Named, Reachable PH Partner — CARD MRI

| Requirement | Status |
|---|---|
| Org name | **CARD MRI (Philippines)** — Leading microfinance group, ~8M members |
| Contact status | Physical office accessible, can walk in |
| What they currently do | Microfinance, microinsurance, microsavings — has existing merchant lending programs, field officers doing regular village visits |
| Why they need this | Can be validated in-person via needs assessment interview |
| What they have | Field officer network, cooperative groups with transaction history, micro-insurance/savings products to cross-sell, trust in underserved communities |

**Action**: Walk into CARD MRI office. Ask to speak to someone in their micro-enterprise or member services unit. Validate: do they see merchant cashflow invisibility as a pain point? Do they already have a tool for this?

Once confirmed, document:
- Name and title of contact person
- Current process for merchant lending decisions
- Specific pain points they mention about cashflow visibility
- Existing digital tools they use (if any)
- What would make them adopt a voice-led solution

### 2. RRL (7-10 Studies Required)

| Theme | What to Find | Why |
|---|---|---|
| Sari-sari store economics | Profit margins, cashflow patterns, common failure points | Baseline for what "distress" looks like |
| ASR accuracy in PH languages | Tagalog, Cebuano, Taglish WER rates under noise | Technical feasibility evidence |
| Voice UI among low-literacy users | Adoption rates, friction points, trust factors | UX validation |
| Digital vs. paper ledger accuracy | Error rates, compliance, preference studies | Evidence that voice is better |
| Merchant lending in PH | Current practices, default rates, barriers | FSP business case grounding |
| Biometric/voice data privacy | DPA compliance, consent frameworks | Ethics defense |

### 3. FSP Business Case (3 Concrete Metrics)

| Metric | How to Measure | Why FSP Cares |
|---|---|---|
| Portfolio risk visibility | % of merchants flagged before missed payment | Reduces default rate |
| Automated underwriting | Loan approval time before vs. after | Reduces operational cost |
| Member retention | Churn rate comparison | Reduces acquisition cost |

Each needs a paragraph tying the voice data to a measurable FSP outcome.

### 4. Demo Script (Full, Like Alagad's)

```
WEEK 1:
Merchant → Voice: "Bumili ako 3 case softdrinks, 900 piso. Benta kahapon 1,200."
Bot → "Expense: ₱900 (inventory). Revenue: ₱1,200. Net: ₱300. Keep it up!"

WEEK 4:
Merchant → Voice: "Mabagal benta ngayon. 500 lang kahapon. Wala masyado customer."
Bot → "Noted. Revenue ₱500. No new inventory recorded. Your cashflow is down 58% from last week. Want me to flag this to your coop officer?"

COOP DASHBOARD:
⚠️ Maria's Store (Member #2041)
- Revenue: down 40% for 2 weeks
- Cash reserve: ₱300 (below 1-week expense threshold)
- Chatbot detected phrase: "mabagal ang benta"
- Risk level: Moderate-High
- Recommended: Field officer check-in within 7 days + short-term credit line adjustment offer
```

### 5. Technical Risk Mitigation

| Risk | Mitigation |
|---|---|
| ASR fails in noisy market | Fallback to text input (merchant types instead of speaks); keyword spotting as lighter alternative to full transcription |
| Low connectivity | Offline mode — runs on-device Whisper, syncs when connected |
| Dialect coverage gaps | Start with Tagalog and Taglish only; narrow scope for demo |
| LLM hallucinates amounts | Structured entity extraction with validation rules (e.g., "₱900" must be a number within 3x of typical range) |

### 6. Privacy & Ethics

Voice data is biometric — regulated under PH Data Privacy Act. Need:

- Consent flow at first use (opt-in, explain what data is stored, who sees it)
- Data minimization: store text transcript, discard raw audio after processing
- Opt-out: merchant can delete history at any time
- FSP access: coop sees only aggregated risk flags, not merchant transaction details

### 7. Competitive Landscape

| Competitor | What They Do | Gap Alagad Fills |
|---|---|---|
| GCash / Maya | Digital payments, basic transaction history | No voice input, no distress prediction, no coop integration |
| Lista | PH expense tracking app | Requires typing, no FSP backend, no intervention engine |
| Paper ledger | Current default | High error, no analytics, no distress signals |
| Other hackathon teams | Likely building budgeting apps | Will not have voice + FSP intervention pipeline |

### 8. Implementation Timeline

| Phase | What | By When |
|---|---|---|
| 0 | Find PH coop partner, secure interest | ASAP |
| 1 | Build ASR + LLM pipeline prototype (Tagalog only) | Phase 2 deadline (Aug 28) |
| 2 | Pilot with 10-20 merchants + coop field officers | Sept |
| 3 | Train prediction model on pilot data | Sept-Oct |
| 4 | Manila finals demo | Nov 4-6 |

---

## Critical Path Decision

**If you pursue this:** The first step is NOT code. Walk into CARD MRI, find the right person, and get 30 minutes to understand their merchant lending pain points. Everything else builds on that conversation.

Without that partner conversation, this is just a better-written hypothetical.

## Immediate Next Step

1. **Go to CARD MRI office** — identify yourself as a hackathon participant, ask for micro-enterprise unit
2. **Prepare 5 questions** to validate the pain point:
   - How do you currently assess merchant creditworthiness?
   - What data do you wish you had but don't?
   - How many merchant loan defaults happen because you didn't see cashflow trouble coming?
   - Would a voice-based tool that merchants already use (WhatsApp/Viber) help your field officers?
   - What would make you pilot something like this?
3. **If CARD MRI confirms the pain point** — get a contact person and document the conversation. You now have a real partner.
4. **If CARD MRI says "not our problem"** — ask who else in their network serves sari-sari stores and whether they can refer you.
