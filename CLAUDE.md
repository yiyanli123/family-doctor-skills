# Claude Code Instructions

This repository contains two health-triage instruction sets adapted from Codex Skills. They can also be used as Markdown instruction sets by Claude Code and other vibe coding / agent apps:

- English: `family-doctor-en/SKILL.md`
- Simplified Chinese: `family-doctor-zh/SKILL.md`

Use these instructions when the user asks for home-health triage, first-aid guidance, symptom red-flag checks, medication-safety boundaries, poisoning/accidental ingestion routing, or care escalation.

## How To Choose

- Use `family-doctor-en/` for English-speaking users.
- Use `family-doctor-zh/` for Chinese-speaking users or mainland China care-routing questions.
- If the user mixes languages, answer in the user's preferred language and load the matching folder.

## Workflow

1. Read the matching `SKILL.md`.
2. Check emergency red flags before giving home-care advice.
3. Load only the relevant files under that folder's `references/`.
4. Identify special-risk status: child, older adult, pregnancy/postpartum, allergy/anaphylaxis history, chronic disease, immune compromise, anticoagulant use, recent surgery, or complex medication use.
5. Classify the situation: emergency services, ER/ED, urgent/same-day care, routine clinician follow-up, or home care with monitoring.
6. Give clear next steps, what to avoid, red flags to watch for, and when to seek care.

## Medical Boundaries

Do not:

- Make definitive diagnoses.
- Prescribe medications.
- Recommend prescription-only dosing.
- Tell users to start antibiotics, steroids, antivirals, anticoagulants, opioids, sedatives, or controlled medications.
- Advise stopping or changing prescribed medicine without clinician/pharmacist input unless there is an immediate emergency reaction, in which case escalate.
- Encourage delaying emergency care.

If symptoms may be life-threatening, tell the user to call local emergency services immediately.

## Source Discipline

For current medical guidance, especially medication dosing, vaccines, infectious-disease recommendations, recalls, or local emergency routing, verify with current authoritative sources. Prefer public-health agencies, first-aid organizations, poison-control organizations, professional societies, and government emergency-care resources.
