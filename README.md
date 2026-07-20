# skills

Personal agent skills collection — installable via the `skills` CLI. Each
skill lives in its own folder with a `SKILL.md` at minimum.

## Skills

| Skill | Description |
|---|---|
| [review-architecture](review-architecture/) | Deep architecture audits — full endpoint mapping, user journey analysis, and prioritized fix plans |
| [resume-builder](resume-builder/) | Add, edit, and polish resume bullets with action verbs, business metrics, and bolded tech |

## Install

List available skills:

```bash
npx skills add PeytonLi/skills --list
```

Install a specific skill:

```bash
npx skills add PeytonLi/skills --skill resume-builder
npx skills add PeytonLi/skills --skill review-architecture
```

Add `-g` to install globally.

## Structure

```
skills/
├── LICENSE
├── review-architecture/
│   ├── SKILL.md
│   └── README.md
└── resume-builder/
    ├── SKILL.md
    └── REFERENCE.md
```

## License

MIT — see [LICENSE](LICENSE).
