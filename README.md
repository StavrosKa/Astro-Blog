# 🌵 My Personal Digital Garden

Welcome to the repository of my personal blog. This project is built using **Astro v6**, styled with **Tailwind CSS**, and designed as a clean digital garden for AI and technology ideas.

---

## 🔗 Quick Links

* **Live Website:** [👉 https://stavroskarelis.com]
* **Deployment Dashboard:** [Netlify App](https://app.netlify.com)
* **Domain Manager:** [Porkbun](https://porkbun.com)

---

## 🛠️ Project Structure & Customization Reference

Here is a quick cheat sheet for when I want to update the site:

### Repository guide

GitHub shows the latest commit message beside each file or folder. Older labels such as `v2` and `v8` describe past commits, not the purpose of those items. Use this guide to find what to edit; new commits should describe the actual change.

| File or folder | Purpose |
| --- | --- |
| `.github/` | GitHub Actions checks, dependency updates, and contribution templates. |
| `.vscode/` | Recommended extensions and workspace settings for Visual Studio Code. |
| `.zed/` | Editor, formatting, and language-server settings for Zed. |
| `public/` | Static files served directly, including the site icon and article media. |
| `public/images/` | Article images and animations, including the FolioEcho walkthrough GIF. |
| `scripts/` | Helpers for generating site icons and the social preview card. |
| `src/` | Site pages, layouts, components, styles, configuration, and content. |
| `src/content/post/` | Published articles and drafts in Markdown or MDX. |
| `src/content/note/` | Short notes and updates. |
| `src/content/tag/` | Optional titles and descriptions for tag pages. |
| `src/content.config.ts` | Content schemas, required metadata, and collection loaders. |
| `src/site.config.ts` | Site identity, navigation, social links, and code-block options. |
| `.editorconfig` | Shared indentation, character encoding, and line-ending rules. |
| `.example.env` | Example environment variables for optional Webmention features. |
| `.gitignore` | Local files, dependencies, secrets, and build output excluded from Git. |
| `.nvmrc` | Node.js version used by the project. |
| `.prettierignore` | Files excluded from Prettier formatting. |
| `.prettierrc.js` | Prettier rules and Astro/Tailwind formatting plugins. |
| `LICENSE` | MIT license terms and attribution. |
| `README.md` | Project overview, repository guide, and publishing instructions. |
| `astro.config.ts` | Astro integrations, Markdown rendering, image handling, and environment schema. |
| `biome.json` | Biome formatting and code-checking rules. |
| `package.json` | Project dependencies and development/build commands. |
| `package-lock.json` | Exact dependency versions for npm installations. |
| `pnpm-lock.yaml` | Exact dependency versions for pnpm installations. |
| `pnpm-workspace.yaml` | pnpm dependency overrides and permitted package build scripts. |
| `tailwind.config.ts` | Tailwind theme and typography configuration. |
| `tsconfig.json` | TypeScript checks, path aliases, and project file selection. |

### Publishing an article

1. Add a Markdown file to `src/content/post/` using the frontmatter template below. Use an ISO date such as `2026-11-04` and set `draft: false` when ready to publish.
2. Put article media in `public/images/` and reference it with a site path such as `/images/folioecho-tour.gif`, never a local computer path.
3. Use the site's `:::tip` or `:::note` directives for callouts.
4. Install dependencies with `npm ci`, then run `npx astro check` and `npm run build`.
5. Commit with a descriptive message, such as `Publish FolioEcho hackathon article and walkthrough GIF`, and push to `main` for the connected Netlify deployment.

### 1. Configuration & Settings
* **Global Config:** `src/site.config.ts` — Change site title, description, language, and social links.
* **Tailwind Styling:** `src/styles/global.css` — Modify global dark/light theme colors.

### 2. Content Management
* **Blog Posts:** `src/content/post/` — Add new `.md` or `.mdx` files here for longer articles.
* **Short Notes:** `src/content/note/` — Add short, quick thoughts or micro-posts here.

### 3. Frontmatter Template
When creating a new blog post, use this snippet at the very top of the file:

```markdown
title: "Post Title (Max 60 chars)"
description: "SEO description (50-160 chars)"
publishDate: "2026-11-04"
tags: ["tech", "thoughts"]
draft: false
```
### 4. Site Map

```markdown
├── 🏠 Home
│   ├── 📌 Pinned Posts
│   ├── 📝 Latest Posts
│   └── 📒 Recent Notes
│
├── 👤 About
│   ├── Who I am
│   ├── What I do
│   └── Links
│
├── 📝 Blog
│   ├── AI
│   ├── Programming
│   ├── Tutorials
│   └── Productivity
│
├── 📒 Notes
│   ├── Ideas
│   └── References
│
├── 🔍 Search
│
└── 🌙 Theme Toggle
```
