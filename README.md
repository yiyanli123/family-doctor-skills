# Family Doctor Skills

[中文](README.zh-CN.md) | [Trust & Safety](TRUST.md) | [Contributing](CONTRIBUTING.md)

English-first and Chinese-first health-triage instruction sets for Codex Skills and other vibe coding / agent apps, including Claude Code, Cursor, Windsurf, Cline, Roo Code, and tools that can read repository-level Markdown instructions.

> Medical safety note: these skills do not replace professional diagnosis, prescriptions, emergency services, or clinician care. If symptoms may be life-threatening, call local emergency services immediately.

## Versions

| Skill | Language | Best for |
| --- | --- | --- |
| `family-doctor-en` | English | English-speaking users, 911/999/112/000, urgent care, ER/ED, primary care/GP, Poison Control |
| `family-doctor-zh` | Simplified Chinese | Chinese users, mainland China care routing, `120`, community clinic/outpatient/ER triage |

## What They Do

- Identify red flags and decide whether the situation needs emergency services, ER/ED, urgent care, same-day clinic, primary care, pharmacist advice, or home monitoring.
- Give practical home-care and first-aid steps for mild situations.
- Explain what not to do, such as unnecessary antibiotics, unsafe burn remedies, duplicate cold medicines, or delaying care for stroke-like symptoms.
- Handle higher-risk groups more conservatively: children, older adults, pregnancy/postpartum, allergy-prone users, chronic disease, immunocompromised users, anticoagulant users, and people taking complex medications.
- Help users prepare information for a medical visit: symptom timeline, temperature log, medication list, allergy history, photos, and medicine/chemical packaging.

## Use Cases

- Fever, cough, sore throat, cold/flu-like symptoms
- Vomiting, diarrhea, stomach pain, food poisoning concerns
- Cuts, bleeding, burns, sprains, falls, head injury
- Allergic reactions, rash, insect stings
- Child fever, older adult weakness/confusion, pregnancy symptoms, chronic disease worsening
- Medication mistake, accidental ingestion, chemical exposure
- Deciding home care vs clinic vs urgent care/ER vs emergency services

## Not For

- Definitive diagnosis
- Prescription medication decisions
- Replacing emergency services
- Long-term chronic disease management plans
- Mental health crisis response

If there is severe trouble breathing, chest pain, stroke signs, unconsciousness, seizure, severe allergic reaction, uncontrolled bleeding, severe trauma, serious burns, or poisoning with serious symptoms, call emergency services.

## Installation

Clone this repository, then copy either or both skill folders into your Codex skills directory.

```bash
cp -R family-doctor-en ~/.codex/skills/
cp -R family-doctor-zh ~/.codex/skills/
```

Then restart Codex or reload skills.

## Other Vibe Coding And Agent Apps

This repository is designed to be useful beyond Codex. The folders are plain Markdown instruction sets, so other vibe coding and agent apps can read and apply them even if they do not natively support Codex Skills.

- `CLAUDE.md` for Claude Code
- `AGENTS.md` for general agent tools that read repository-level instructions
- `family-doctor-en/SKILL.md` and `family-doctor-zh/SKILL.md` as the main instruction bodies
- `references/` files as focused medical-safety and triage references

Apps such as Claude Code, Cursor, Windsurf, Cline, Roo Code, and similar tools can use this repository by reading the matching `SKILL.md` and only the relevant `references/` files.

## How To Use

### Use With Codex

After copying the skill folders into `~/.codex/skills/`, restart Codex or reload skills. Then ask Codex to use the language-specific skill:

```text
Use family-doctor-en to help me assess whether these symptoms are dangerous and whether I should use home care, urgent care, the ER, or emergency services.
```

```text
请使用 family-doctor-zh，帮我判断这个症状是否危险，应该居家观察、去门诊、去急诊，还是拨打 120。
```

### Use With Claude Code

Open this repository in Claude Code. Claude Code should read `CLAUDE.md` as project-level guidance. Then ask it to use the matching instruction set:

```text
Use the English Family Doctor instructions in this repository to triage this situation: ...
```

```text
请根据这个仓库里的中文家庭医生指令，帮我判断这个症状是否危险：……
```

### Use With Cursor, Windsurf, Cline, Roo Code, Or Similar Apps

Open the repository in the app and point the agent to:

- `AGENTS.md` for general repository instructions
- `family-doctor-en/SKILL.md` for English use
- `family-doctor-zh/SKILL.md` for Chinese use
- The relevant files under `references/` for details

Example prompt:

```text
Read AGENTS.md, then use family-doctor-en/SKILL.md and relevant reference files to help triage this home-health question: ...
```

Chinese example:

```text
请先读取 AGENTS.md，然后使用 family-doctor-zh/SKILL.md 和相关 references 文件，帮我做居家健康分流：……
```

## What To Include

- Age and sex
- Pregnancy/postpartum status if relevant
- Main symptom or injury
- When it started and whether it is getting worse
- Temperature, blood pressure, glucose, oxygen saturation if available
- Breathing, alertness, fluid intake, and urine output
- Chronic conditions and current medications
- Allergy history
- Whether the person is a child, older adult, immunocompromised, allergy-prone, pregnant, on anticoagulants, or taking many medicines

## Examples

```text
Use family-doctor-en: my 4-year-old has a fever of 102.5 F and a cough. She is drinking but more tired than usual. What should I watch for, and when should we go to urgent care or the ER?
```

```text
Use family-doctor-en: my 82-year-old mother fell and hit her head. She takes a blood thinner but says she feels okay. What should we do?
```

```text
Use family-doctor-en: I am 28 weeks pregnant and have a severe headache with some swelling. Should I call my doctor or go to the ER?
```

```text
Use family-doctor-en: I ate shrimp and now have hives and mild lip swelling. I can breathe and talk. What should I do?
```

## Output Style

Both versions prioritize actionable triage:

1. Risk level
2. What to do now
3. What can be done at home
4. What to avoid
5. Red flags to watch for
6. When to seek clinic/urgent care/ER/emergency services
7. What information to bring if seeking care

## Reliability & Safety

These skills should be described as **safety-oriented and source-informed**, not as a substitute for medical care. Their reliability comes from process design:

- Conservative triage: emergency red flags are checked before home-care advice.
- Clear escalation: high-risk symptoms route to emergency services, ER/ED, urgent care, or same-day clinician contact.
- Special-population caution: children, older adults, pregnancy/postpartum, allergy-prone users, chronic disease, immunocompromised users, and anticoagulant users are handled with a lower threshold for care.
- Explicit boundaries: the skills do not provide definitive diagnoses, prescription decisions, or personalized medication changes.
- Auditable content: guidance is split into readable reference files, so contributors can review and improve specific areas.
- Source-informed design: key safety patterns follow public guidance from organizations such as CDC, American Red Cross, Poison Control, ACOG, and local emergency-care resources.
- Current-guidance rule: for time-sensitive topics such as medication dosing, vaccines, infectious-disease rules, recalls, or local emergency routing, the skill instructs Codex to verify current authoritative sources.

Useful source examples:

- [CDC flu signs and symptoms](https://www.cdc.gov/flu/signs-symptoms/index.html)
- [American Red Cross first aid resources](https://www.redcross.org/take-a-class/resources/learn-first-aid)
- [Poison Control](https://www.poison.org/)
- [ACOG urgent maternal warning signs](https://www.acog.org/womens-health/infographics/urgent-maternal-warning-signs)

## Repository Structure

```text
.
├── family-doctor-en/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
│       ├── english-localization.md
│       ├── children.md
│       ├── fever-respiratory.md
│       ├── first-aid-injuries.md
│       ├── gastro-poisoning.md
│       ├── medication-safety.md
│       ├── older-adults.md
│       ├── output-patterns.md
│       ├── pregnancy-allergy-high-risk.md
│       └── red-flags.md
└── family-doctor-zh/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
        ├── china-localization.md
        ├── children.md
        ├── fever-respiratory.md
        ├── first-aid-injuries.md
        ├── gastro-poisoning.md
        ├── medication-safety.md
        ├── older-adults.md
        ├── output-patterns.md
        ├── pregnancy-allergy-high-risk.md
        └── red-flags.md
```

## Safety Philosophy

These skills are intentionally conservative. They are designed to help users decide what to do next, not to make final diagnoses. If a response says to seek urgent care, ER/ED care, or emergency services, real-world medical action should come first.

For more detail, see [Trust & Safety](TRUST.md).

## Contributing

Issues and pull requests are welcome, especially for:

- Clearer English or Chinese triage templates
- Better special-population guidance
- Country-specific emergency and care-routing notes
- Authoritative medical source updates
- Safer boundaries and common-mistake warnings

Medical-content changes should include authoritative sources where possible and preserve the conservative triage principle.

For contribution rules, see [Contributing](CONTRIBUTING.md).
