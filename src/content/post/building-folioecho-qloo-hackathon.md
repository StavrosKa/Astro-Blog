---
title: "What I Learned Building FolioEcho for the Qloo Hackathon"
description: "A short, honest look at building an AI agent for independent bookshops, and what a hackathon taught me about constraints, evidence and shipping."
publishDate: "2026-11-04"
tags: ["ai", "hackathon", "qloo", "building", "software-development"]
draft: false
pinned: false
---

> *“An idea only becomes useful when it survives a real constraint.”*

A few weeks ago I entered the Qloo Agentic Hackathon, on my own, with one question: could an AI agent suggest cultural events for a small independent bookshop while respecting the shop’s stock and planning constraints?

The answer became **FolioEcho**.

---

## 📚 The Idea

Qloo understands how culture connects: a book to a musician, a musician to a film. FolioEcho takes a bookshop’s catalogue, asks Qloo for those connections and turns them into event ideas, such as a reading night with a matching playlist or a film evening with a discussion. Film screenings still require a separate permissions check.

The twist is that **stock is a hard constraint**. Proposals involving unavailable books are rejected. If stock changes, the what-if workflow can rebuild the affected proposals.

---

## 🛠️ What Actually Happened

I built it with Astro, TypeScript, React and React Flow. The agent resolves book titles, retrieves evidence from Qloo, validates each proposal and shows every step in an agent trace. You can even remove a cultural connection and watch the plan change.

I used the Gemini API to help organise catalogue tags into broader themes and turn selected references into editable event titles and activities. Qloo supplied the cultural evidence; Gemini helped make it usable without changing the evidence or scores.

Three things surprised me:

- **Live calls are slow.** A full live run can take several minutes, so saved Qloo results became the default and live runs became optional.
- **Evidence beats fluent text.** A language model alone can sound convincing, but its wording does not establish a cultural connection. Qloo gave me recorded results I could inspect.
- **Honesty needs labels.** Some early screens used demo data, so I marked them clearly instead of letting them pretend to be real.

---

## ⚖️ How Proposals Are Ranked and Saved

Behind the event proposals, I built a ranking algorithm that groups books by shared themes, retrieves Qloo connections, and checks stock, duration, and capacity. It then ranks eligible proposals using four weighted factors and selects a varied mix of books and event types.

```text
Cultural affinity    ████████  40%
Discovery potential  █████     25%
Book coverage        █████     25%
Feasibility          ██        10%
```

These weights are prototype choices, not proven predictors of event success. Discovery potential favours less popular cultural references; it does not establish what is new to a particular reader.

SQL storage—SQLite locally and PostgreSQL online—keeps the catalogue, saved plans, revisions, and cached Qloo results. This lets users revisit plans, compare changes, and reuse recent results without repeating API calls.

---

## 🤖 What I’d Tell Another Builder

Start with constraints, not features. Show your evidence. Say what is real and what is a demo. And ship before it feels perfect, because I had to follow my own advice from [Why Developers Overthink Everything](/posts/why-devs-overthink/).

:::tip
If your AI idea would work the same without the data source, you’re probably building the wrong thing.
:::

FolioEcho is still a prototype. Whether its ideas help real bookshops reach new readers is the next question to test.

You can try it at [folioecho.netlify.app](https://folioecho.netlify.app/) and read the code on [GitHub](https://github.com/StavrosKa/folioecho).

<img src="/images/folioecho-tour.gif" alt="FolioEcho walkthrough showing the overview, catalogue, discovery studio, cultural map and event planner" width="1440" height="860" loading="lazy" decoding="async" />
