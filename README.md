# rishirameshstudio.github.io

Personal portfolio site, served as static files by GitHub Pages. No build step.

## Structure

```
index.html              page markup
assets/css/styles.css   styles
assets/js/main.js       menu, scroll reveal, clock
assets/images/          logo, avatar, project images
AGENTS.md               instructions for AI coding agents
.claude/settings.json   Claude Code permissions that enforce AGENTS.md's git rules
```

## Local preview

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy

Push to `main`. GitHub Pages publishes the repository root.
