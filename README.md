[README.md](https://github.com/user-attachments/files/32048136/README.md)
<div align="center">

# 🔍 Zero-Setup SEO Skill Pack for Claude

### A complete, connector-free SEO workflow — audits, briefs, keyword research, link strategy, and full article writing — built entirely as Claude Skills.

![Skills](https://img.shields.io/badge/skills-12-blue)
![Setup](https://img.shields.io/badge/setup-zero%20config-brightgreen)
![Connectors](https://img.shields.io/badge/connectors-none%20required-lightgrey)
![License](https://img.shields.io/badge/license-TBD-yellow)
![Made for](https://img.shields.io/badge/built%20for-Claude-6A5ACD)

</div>

---

## 📋 Table of Contents

- [Why this exists](#-why-this-exists)
- [How it works](#-how-it-works)
- [What's inside](#-whats-inside)
  - [🧭 seo-master (router)](#-seo-master-router)
  - [🔎 page-audit](#-page-audit)
  - [📝 content-brief](#-content-brief)
  - [🎯 keyword-deep-dive](#-keyword-deep-dive)
  - [🗺️ topic-cluster-planning](#️-topic-cluster-planning)
  - [🧩 semantic-gap-analysis](#-semantic-gap-analysis)
  - [🏅 eeat-audit](#-eeat-audit)
  - [🔗 linkbuilding](#-linkbuilding)
  - [🎙️ expert-interview](#️-expert-interview)
  - [⭐ featured-snippet-optimizer](#-featured-snippet-optimizer)
  - [✍️ write-content](#️-write-content)
  - [🔧 improve-content](#-improve-content)
- [Common workflows](#-common-workflows-chained-skills)
- [Installation](#-installation)
- [Usage](#-usage)
- [What this pack can't do](#-what-this-pack-cant-do-be-honest-with-your-users-about-this)
- [FAQ](#-faq)
- [License](#-license)
- [Contributing](#-contributing)

---

## 💡 Why this exists

Most "SEO tools" assume you already have a stack: Google Search Console
access, a paid rank tracker, a backlink database, a keyword-volume API.
That's a real barrier — either in cost, setup time, or account access — for
solo creators, small teams, and anyone who just wants a fast, competent
second opinion on a page or a plan for a new article.

This pack takes a different approach. Every skill in it **researches
live** — it Googles the keyword, fetches the actual page, reads the actual
top-ranking competitors — the same way a sharp human strategist would if
you handed them a laptop and no tools. The trade-off is explicit and
worth understanding before you use this: you get real, current,
competitor-grounded analysis with **zero setup**, but you don't get
historical trend lines, exact monthly search volumes, or a verified
backlink count. If you need those specific numbers, pair this pack with a
connector-backed tool (Google Search Console, Semrush, Ahrefs, DataForSEO)
— this pack intentionally doesn't try to fake having one.

## ⚙️ How it works

Each skill below is a self-contained instruction set (a `SKILL.md` file)
that tells Claude how to behave when a particular kind of SEO task comes
up — what research to do, what role to take on, and what the final
deliverable should look like. You don't invoke them by name; you just ask
for what you want in plain language, and the **`seo-master`** router reads
the request and hands it to the right skill (or chains a few together).

```
 You: "audit my pricing page and then rewrite the weak parts"
                        │
                        ▼
                 🧭 seo-master
                        │
        ┌───────────────┴───────────────┐
        ▼                                ▼
   🔎 page-audit                  🔧 improve-content
   (finds the problems)           (fixes what it found)
```

---

## 📦 What's inside

12 skills total: **1 router + 11 workers.** Every worker skill needs
nothing but Claude's built-in web search and page-fetch — no API keys, no
signup, no data export to paste in.

### 🧭 seo-master (router)

The traffic controller. Reads every incoming SEO request, matches it
against the table of workers below, and either routes to one skill or
chains several in sequence for compound requests ("audit this and then fix
it"). If a request needs real numeric data this pack can't produce (exact
search volume, a verified backlink count, Core Web Vitals field data), it
says so plainly instead of guessing.

### 🔎 page-audit

**Input:** a single URL.
**What it does:** fetches the page, identifies its primary target
keyword, Googles that keyword, reads the top 3 ranking competitors in
full, and scores the page across seven dimensions — not a generic
checklist, but competitive, "what actually outranks this page and why"
analysis.
**Good for:** "is this page any good," "why is this underperforming," a
fast gut-check before a bigger content investment.

### 📝 content-brief

**Input:** a target keyword (plus optional audience/tone context).
**What it does:** Googles the keyword, reads the top 10 ranking pages,
classifies search intent, maps the content gap between what's ranking and
what's missing, and hands back a writer-ready brief — structure, outline,
on-page targets.
**Good for:** briefing a freelance writer, or handing straight to the
`write-content` skill below.

### 🎯 keyword-deep-dive

**Input:** a target keyword (optionally, a URL you're already targeting
it with).
**What it does:** full SERP research — intent, the top 3 competitors read
in depth, what it would actually take to rank — compiled into a concrete
90-day plan.
**Good for:** deciding whether a keyword is even worth pursuing before you
commit writing time to it.

### 🗺️ topic-cluster-planning

**Input:** a seed topic or broad keyword (e.g. "email marketing").
**What it does:** researches the whole topic space — top-10 results,
People Also Ask, related searches — and designs a hub-and-spoke
architecture: one pillar page plus supporting articles, with an internal
linking plan that concentrates authority on the pages that matter.
**Good for:** planning a brand-new content area from zero, not just one
article.

### 🧩 semantic-gap-analysis

**Input:** your page's URL **and** the target keyword.
**What it does:** compares your page's entities, subtopics, and
relationships against the top-ranking competitors' and returns the exact
list of what's structurally missing — not "add more depth," but the
specific nodes your content is missing from Google's semantic model of the
topic.
**Good for:** a page that ranks, but not in the top 3, and you want to
know precisely why.

### 🏅 eeat-audit

**Input:** a page URL (or pasted content if the fetch fails).
**What it does:** reads the page the way a Google quality rater would and
scores it on Experience, Expertise, Authoritativeness, and Trust — then
tells you exactly what's missing and how a real practitioner would add it
(this skill is calibrated to notice the difference between a claimed
credential and content that actually reads like it was written by someone
who did the thing).
**Good for:** trust and quality issues that are quietly capping a page's
ranking ceiling.

### 🔗 linkbuilding

**Input:** your domain or a URL (optionally, your niche and any
constraints — "no outreach budget," "already tried guest posting," etc.).
**What it does:** classifies your site's authority phase from visible
signals (domain age, homepage content) and recommends phase-appropriate
tactics from a library of nine detailed playbooks — everything from
low-effort wins (testimonials, citations) to full outreach campaigns.
**Good for:** a concrete, prioritized link-building plan instead of a
generic "get more backlinks" suggestion.

### 🎙️ expert-interview

**Input:** a topic to discuss — nothing else.
**What it does:** this is the one skill in the pack that does zero web
research. It's a pure conversation: Claude asks you 2–4 sharp, adaptive
questions designed to pull out first-hand experience, specific numbers,
and surprising outcomes — the kind of thing no amount of web searching
could ever produce — and compiles it into a knowledge document.
**Good for:** feeding real expertise into `write-content` or
`improve-content` so the output doesn't read like generic AI filler.

### ⭐ featured-snippet-optimizer

**Input:** target keyword **and** your page's URL (must already rank
positions 1–5 — this skill won't help a page that isn't close already).
**What it does:** checks whether a featured snippet exists for the
keyword, who holds it, and what format Google is pulling from — then
rewrites the relevant section of your page to match that format.
**Good for:** capturing extra clicks on a keyword you're already
competitive on without changing your ranking position.

### ✍️ write-content

**Input:** a topic or target keyword (optionally, a brief from
`content-brief` and/or a knowledge document from `expert-interview` to
skip the research phase).
**What it does:** a full four-phase pipeline — research, content-type
decision, knowledge extraction, and writing — that produces a complete,
publish-ready article. Comes with a built-in anti-AI-slop ruleset (banned
vocabulary, banned phrases, banned structural patterns) so the output
reads like a practitioner wrote it, not a press release.
**Good for:** the actual first draft, once you know what to write about.

### 🔧 improve-content

**Input:** the URL of an existing, underperforming page.
**What it does:** fetches and reads the current page in full, researches
the live SERP for its primary keyword, and rewrites it — same anti-slop
ruleset as `write-content` — with better structure and demonstrated
expertise, aimed at actually outranking what's currently beating it.
**Good for:** refreshing an old page instead of starting from scratch.

---

## 🔄 Common workflows (chained skills)

You don't have to invoke these steps individually — just describe the
outcome you want and `seo-master` will chain them.

| Goal | Chain |
|---|---|
| **Write a brand-new article** | 🎙️ `expert-interview` (if you have a SME) → 📝 `content-brief` → ✍️ `write-content` |
| **Fix an underperforming page** | 🔎 `page-audit` → 🧩 `semantic-gap-analysis` → 🔧 `improve-content` |
| **Launch a new content area** | 🗺️ `topic-cluster-planning` → 📝 `content-brief` (per spoke) → ✍️ `write-content` (per spoke) |
| **Squeeze more clicks from existing rankings** | ⭐ `featured-snippet-optimizer` (rank 1–5) *or* 🏅 `eeat-audit` + 🔧 `improve-content` (rank 6+) |

---

## 🛠️ Installation

Drop all 12 folders into your Claude skills directory so each keeps its own
`SKILL.md`:

```
your-skills-folder/
├── seo-master/SKILL.md
├── page-audit/SKILL.md
├── content-brief/SKILL.md
├── keyword-deep-dive/SKILL.md
├── topic-cluster-planning/SKILL.md
├── semantic-gap-analysis/SKILL.md
├── eeat-audit/SKILL.md
├── linkbuilding/SKILL.md
├── expert-interview/SKILL.md
├── featured-snippet-optimizer/SKILL.md
├── write-content/SKILL.md
└── improve-content/SKILL.md
```

Exactly how you register a skills folder depends on which Claude surface
you're using (Claude.ai project skills, Claude Code, the Claude API with a
skills-aware harness, etc.) — check that product's own docs for the
specific registration step; this repo just provides the skill files.

## 🚀 Usage

Just ask normally:

> "Audit https://example.com/pricing"
> "Write me a blog post about cold brew coffee at home"
> "Plan a topic cluster for a personal-finance blog"
> "Why isn't my page ranking above position 5 for 'best running shoes'?"

`seo-master` reads the request and routes it — you never need to name a
skill by hand. If you *do* want to force a specific skill, just say its
name ("use content-brief for...").

## ⚠️ What this pack can't do (be honest with your users about this)

- No exact monthly search volume, keyword difficulty score, or CPC data
- No historical ranking or traffic trend lines
- No verified backlink count or referring-domain list (only what's
  discoverable via live search)
- No real Core Web Vitals field data (lab/heuristic reads only)

If you need any of the above, pair this pack with a connector-backed
toolset (Google Search Console, Semrush, Ahrefs, or DataForSEO) — this
repo is deliberately scoped to the zero-setup, search-and-fetch-only
half of SEO work.

## ❓ FAQ

**Does this need an API key?**
No. Every skill here uses only Claude's built-in web search and page
fetch.

**Can I use just one or two of these skills instead of the whole pack?**
Yes — each skill folder is fully independent except for `seo-master`,
which needs the others present to route to.

**Will this give me real search volume numbers?**
No — see [What this pack can't do](#-what-this-pack-cant-do-be-honest-with-your-users-about-this).

**Can I modify a skill's instructions?**
Yes, each `SKILL.md` is a plain markdown file — edit the role, steps, or
output format to fit your own workflow.

## 📄 License

**TBD** — see [`LICENSE_TODO.md`](./LICENSE_TODO.md). No license has been
finalized yet; please resolve the provenance question there before treating
this repo as freely reusable.

## 🤝 Contributing

Issues and pull requests are welcome once the license question above is
settled. Good contribution targets: additional playbooks for
`linkbuilding`, more content-type templates for `write-content`, or a new
worker skill that fits the same "zero-setup, self-researching" philosophy.
