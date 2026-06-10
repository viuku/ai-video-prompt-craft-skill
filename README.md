# AI Video Prompt Craft Skill

Hermes Agent skill for writing, improving, and learning cinematic AI video-generation prompts.

This skill distills reusable directing logic from NeoWOW-style and 末日乐园-style prompt corpora, including:

- STYLE LOCK / visual bible structure
- Reference-role anchoring
- Shot-level camera, blocking, motion, light, sound, and continuity rules
- Single-take, hard-cut, occlusion transition, rack-focus, reveal-shot templates
- Action-scene force chains and deadpan comedy staging
- Suspense/horror spatial iron laws, six scene anchors, light-source state machines, and micro-performance chains
- Asset-first workflow: color cards, reference sheets, storyboards, keyframes, blocking diagrams

## Files

- `SKILL.md` — the full Hermes skill.

## Usage

Install or copy this directory into a Hermes profile skills directory, then load it when writing AI-video prompts:

```text
skill_view(name="ai-video-prompt-craft")
```

## Notes

The skill stores distilled craft and production grammar only; it intentionally avoids copying raw prompt dumps or private source corpora.
