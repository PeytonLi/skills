# review-architecture skill

Reusable agent skill for deep architecture audits.

## Repository contents

- `SKILL.md`: Skill definition with required frontmatter (`name`, `description`)
- `README.md`: Publishing and usage instructions
- `LICENSE`: MIT license

## Publish on skills.sh

There is no manual submit form. skills.sh indexes skills that are installable through the `skills` CLI from public repositories.

### 1) Push this repo to GitHub

Make sure the repository is public and `SKILL.md` is at the repository root.

### 2) Verify installability from the CLI

```bash
npx skills add peytonli/review-architecture --list
```

Expected result: your skill appears in the list (for this repo, `review-architecture`).

### 3) Test install of this specific skill

```bash
npx skills add peytonli/review-architecture --skill review-architecture
```

Optional: install globally for all projects.

```bash
npx skills add peytonli/review-architecture --skill review-architecture -g
```

### 4) Verify installation

```bash
npx skills list
```

Once users install your skill, it becomes visible through the skills ecosystem and ranking pipeline.

## Local quality checks

Before pushing changes, validate that `SKILL.md` has:

- Valid YAML frontmatter
- Required fields: `name`, `description`
- Clear usage triggers and step-by-step workflow

## License

MIT (see `LICENSE`)
