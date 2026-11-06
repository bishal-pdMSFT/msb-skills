# MSB skills (SKILL.md layout)

Materialized [MaliciousSkillBench](https://github.com/protectskills/MaliciousSkillBench) identities as individual Agent Skill directories (`ASB04_*/SKILL.md`), not source package archives.

**Source dataset:** [ProtectSkills/MaliciousSkillBench](https://huggingface.co/datasets/ProtectSkills/MaliciousSkillBench) (`primary`)  
**Count:** 9,740 skills (malicious + benign)  
**Labels:** `labels.json`

## Layout

```text
ASB04_000018/
  SKILL.md
  msb_meta.json
labels.json
```

Each `msb_meta.json` carries `benchmark_id`, `label` (`1`=malicious, `0`=benign), `source_ids`, `attack_categories`, and `text_redacted`.

## Safety

This corpus includes **intentionally malicious** skill text for security research and scanner evaluation. Do not execute these skills, follow embedded destinations, or install companion packages from the text.

## Provenance

Re-materialized from the Hugging Face `primary` split (skill text / public skill text). Upstream license and attribution remain with ProtectSkills / MaliciousSkillBench.
