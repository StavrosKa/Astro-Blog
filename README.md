# 🌵 My Personal Digital Garden

Welcome to the repository of my personal blog. This project is built using **Astro v6**, styled with **Tailwind CSS**, and designed as a clean digital garden for AI and technology ideas.

---

## 🔗 Quick Links

* **Live Website:** [👉 Replace this with your live Netlify or Porkbun URL]
* **Deployment Dashboard:** [Netlify App](https://app.netlify.com)
* **Domain Manager:** [Porkbun](https://porkbun.com)

---

## 🛠️ Project Structure & Customization Reference

Here is a quick cheat sheet for when I want to update the site:

### 1. Configuration & Settings
* **Global Config:** `src/site.config.ts` — Change site title, description, language, and social links.
* **Tailwind Styling:** `src/styles/global.css` — Modify global dark/light theme colors.

### 2. Content Management
* **Blog Posts:** `src/content/post/` — Add new `.md` or `.mdx` files here for longer articles.
* **Short Notes:** `src/content/note/` — Add short, quick thoughts or micro-posts here.

### 3. Frontmatter Template
When creating a new blog post, use this snippet at the very top of the file:
```markdown
---
title: "Post Title (Max 60 chars)"
description: "SEO description (50-160 chars)"
publishDate: "17 June 2026"
tags: ["tech", "thoughts"]
draft: false
---

### 4. Site Map
/
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
│   ├── References
│   ├── Snippets
│   └── Learning Journal
│
├── 🔍 Search
│
└── 🌙 Theme Toggle
