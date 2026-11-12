# AGENTS.md

Instructions for AI coding agents (Claude Code, Codex, Cursor, Copilot, and others) working in this repo.

**Maintainers:** edit this file whenever the repo or your preferences change. Keep it short, because agents follow short files more reliably than long ones. Sections marked *(owner)* are your preferences, so change them freely. The other sections describe the repo and should stay accurate.

## Project

Rishi Ramesh's personal portfolio. GitHub Pages publishes it from the repository root of `main`. It is static HTML, CSS and JavaScript, with no build step, no package manager and no framework.

```
index.html              the only page
assets/css/styles.css   all styles; design tokens live in :root
assets/js/main.js       menu toggle, scroll reveal, clock
assets/images/          all images
```

To preview locally, run `python3 -m http.server 8000` and open http://localhost:8000. If port 8000 is taken, use any other free port.

## How to work *(owner)*

- Before changing anything, understand what the request is for. Ask if the request is unclear and the answer would change the result. Otherwise, pick the sensible default and say which one you picked.
- Be a thought partner. If a request works against its own goal, say so and propose something better.
- Make the smallest change that does the job, and prefer deleting code to adding it. Use plain HTML and CSS before JavaScript. Don't add dependencies, build tools or frameworks unless the owner asks for them.
- Don't write or rewrite site content (bio, projects, testimonials, contact details) without asking. The content belongs to the owner.
- Report briefly: what changed, what you verified, and what's left. Skip the reasoning unless asked.
- When handing work to a sub-agent, give it only the goal, the constraints and the expected result, so its judgment isn't biased.

## Conventions

- Markup goes in `index.html`, styles in `styles.css`, behaviour in `main.js`. Don't use inline `style=""` attributes or `<style>`/`<script>` blocks.
- Reuse the custom properties in `:root` (`--ink`, `--muted`, `--line`, `--page-gutter`, `--ease`, and so on) rather than hard-coding colours or spacing.
- Filenames are lowercase and hyphenated, with no spaces. Images go in `assets/images/`.
- Export images at about twice their largest displayed size and compress them, aiming for under 500 KB each.
- Use relative paths for every asset.
- When you touch animations or the menu, keep `prefers-reduced-motion` support and the existing ARIA attributes working.

## Verify before calling it done

- Load the page locally and confirm the browser console shows no errors and no requests fail.
- Check the page at desktop width (about 1440px) and mobile width (about 390px).
- Test everything you touched: opening and closing the menu (including with Escape), the scroll reveal, and the clock.
- When a refactor must not change the look, take full-page screenshots before and after at the same viewport, with reduced motion on and the clock fixed. The two must be identical.
- Check against the real page once. Don't build a toy reproduction first. If a check is still failing after a few attempts, stop and report what you know.
- Stop any server or process you started.

## Git *(owner)*

For Claude Code, `.claude/settings.json` enforces these rules: it prompts before any commit or push and removes attribution. Other tools rely on this section alone, so keep the two in sync.

- Don't commit or push unless asked. `main` deploys straight to the live site, so work on a branch.
- Never credit Claude, Anthropic or any other AI tool, anywhere: commits (no `Co-Authored-By` trailers), PRs and issues (no "generated with" lines), code comments, docs or branch names.
- Write commit messages with a short subject in the imperative mood ("Fix menu focus", not "Fixed menu focus").

## Known gaps

Delete each line once it's fixed.

- Placeholder content still to replace: `hello@example.studio`, client names, testimonials, stats, journal posts, the "Studio®" wordmark, the NY clock and the meta description.
- The images total about 10 MB. `avatar.png` alone is 7.3 MB but is shown at 216px.
