# skills

Personal agent skills collection installable via the `skills` CLI.

## Skills

| Skill | Description |
|---|---|
| [review-architecture](review-architecture/) | Deep architecture audits — full endpoint mapping, user journey analysis, and prioritized fix plans |
| [resume-builder](resume-builder/) | Add, edit, and polish resume bullets with action verbs, business metrics, and bolded tech |

## Install

```bash
npx skills add peytonli/skills --list
```

To install a specific skill:

```bash
npx skills add peytonli/skills --skill resume-builder
npx skills add peytonli/skills --skill review-architecture
```

Install globally for all projects by adding `-g`.

## Structure

```
skills/
├── review-architecture/
│   ├── SKILL.md
│   ├── README.md
│   └── LICENSE
└── resume-builder/
    ├── SKILL.md
    └── REFERENCE.md
```
