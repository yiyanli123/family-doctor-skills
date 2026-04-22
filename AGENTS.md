# Agent Instructions

This repository provides bilingual home-health triage guidance for Codex Skills and other vibe coding / agent apps such as Claude Code, Cursor, Windsurf, Cline, Roo Code, and tools that can read repository-level Markdown instructions:

- `family-doctor-en/`: English-first skill for English-speaking users.
- `family-doctor-zh/`: Chinese-first skill for Chinese-speaking users, including mainland China routing such as `120`, outpatient/ER/community-care distinctions, and Chinese family scenarios.

Agents should treat these folders as plain Markdown instruction sets. The `SKILL.md` file is the main body, and files under `references/` are loaded only when relevant.

## Default Behavior

When a user asks about symptoms, minor injuries, fever, respiratory illness, vomiting/diarrhea, poisoning, medication mistakes, allergic reactions, burns, wounds, falls, or whether to seek care:

1. Select the matching language folder.
2. Read its `SKILL.md`.
3. Apply red-flag checks before home-care advice.
4. Load only relevant reference files.
5. Use conservative triage.
6. Give practical, plain-language next steps.
7. Make escalation clear: emergency services, ER/ED, urgent care, same-day clinician contact, routine follow-up, or home monitoring.

## Safety Rules

- Do not provide definitive diagnoses.
- Do not prescribe or recommend prescription-only medication decisions.
- Do not encourage self-use of antibiotics for ordinary viral symptoms.
- Do not advise users to stop or change prescribed medication without clinician/pharmacist input unless emergency escalation is needed.
- Do not manage high-risk groups casually.
- Do not delay emergency care.

High-risk groups include infants, children, older adults, pregnant/postpartum users, allergy-prone users, chronic disease, immune compromise, anticoagulant use, recent surgery, and complex medication use.

## Output Expectations

A good answer should include:

- Risk level
- What to do now
- Home care if appropriate
- What to avoid
- Red flags to watch for
- When and where to seek care
- What information to bring if seeking care

Use the user's language by default.
