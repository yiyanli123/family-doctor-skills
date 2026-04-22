# Trust And Safety

[中文](TRUST.zh-CN.md)

Family Doctor Skills are designed as **safety-oriented, source-informed home triage tools**. They help users decide what to do next, but they do not replace clinicians, emergency services, diagnosis, prescriptions, or local medical judgment.

## Why Users Can Have Confidence

### 1. Conservative triage first

The skills check emergency red flags before giving home-care advice. If symptoms suggest immediate danger, the answer should route the user to emergency services, ER/ED care, urgent care, or same-day clinician contact.

### 2. Clear medical boundaries

The skills do not:

- Make definitive diagnoses
- Prescribe medicines
- Recommend starting antibiotics or prescription drugs
- Tell users to stop or change prescribed medicines without clinician/pharmacist input
- Encourage delaying emergency care
- Treat high-risk groups as ordinary low-risk cases

### 3. More caution for high-risk groups

The skills use a lower threshold for care when the user involves:

- Infants or children
- Older adults
- Pregnancy or postpartum symptoms
- Severe allergy or anaphylaxis history
- Asthma, COPD, heart disease, diabetes, kidney/liver disease
- Cancer treatment, transplant medicines, high-dose steroids, or other immune compromise
- Anticoagulants or complex medication use

### 4. Auditable content

Guidance is split into readable reference files such as:

- `red-flags.md`
- `children.md`
- `older-adults.md`
- `pregnancy-allergy-high-risk.md`
- `medication-safety.md`
- `first-aid-injuries.md`

This makes the project reviewable. Contributors can inspect and improve specific parts instead of trusting a hidden prompt.

### 5. Source-informed design

The skills are designed around public safety guidance and common first-aid/triage patterns from sources such as:

- CDC
- American Red Cross
- Poison Control
- ACOG
- Local public-health and emergency-care resources

For information that changes over time, such as medication dosing, vaccines, infectious-disease guidance, recalls, or local emergency routing, the skills instruct Codex to verify current authoritative sources.

## What Reliability Does Not Mean

Reliability does not mean the skill is always correct. It means the project is designed to:

- Avoid overconfident medical claims
- Prefer safer escalation when uncertain
- Keep advice inspectable and improvable
- Make dangerous situations leave the chat and enter real medical care quickly

## How To Evaluate An Answer

A trustworthy answer should:

1. Identify red flags first.
2. Ask only essential missing questions.
3. Give clear next steps.
4. Say what not to do.
5. Explain when to seek care.
6. Be more cautious for high-risk groups.
7. Avoid pretending to diagnose with certainty.

If an answer recommends emergency care, urgent care, or same-day clinician contact, users should prioritize real-world medical action over continued chatting.

## Reporting Problems

Please open an issue if you see:

- Advice that may delay emergency care
- Unsafe medication advice
- Missing warnings for children, older adults, pregnancy, allergies, chronic disease, or immune compromise
- Outdated or unsupported medical claims
- Ambiguous wording that could be misunderstood in a high-risk situation

When reporting, include the prompt, the answer, the risk you noticed, and any authoritative source if available.
