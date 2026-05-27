# Tutorial Content Development Guidelines

These guidelines define the structure, tracks, and formatting requirements for generating tutorial content (MDX). The tutorial generation agent must follow these rules strictly.

---

## 1. Audience Tracks & Badging

Tutorials can target either mixed audiences (non-technical and technical users) or pure technical audiences.

### A. Mixed-Audience Tutorials
If a tutorial covers both conceptual/non-tech and technical/code aspects, you must maintain clear distinction:
1. **📍 Lesson Roadmap**: Place a roadmap blockquote near the top of the file (within the first 30 lines). It must contain a table mapping each section to the target audience:
   - `🟢 Everyone` (for concepts, design, and non-technical explanations)
   - `🔷 Technical` (for code snippets, API syntax, and technical architectures)
   
   *Example:*
   ```markdown
   > **📍 Lesson Roadmap:**
   > | Section | Audience |
   > |:---|:---|
   > | 1. Core Concepts | 🟢 Everyone |
   > | 2. Python SDK Setup | 🔷 Technical |
   ```

2. **Heading Badges**: Every secondary heading (`##`) must start with the appropriate audience badge:
   - `## 🟢 [Heading Title]` — for conceptual and core sections.
   - `## 🔷 [Heading Title]` — for developer code, SDK configurations, or API specs.

3. **No Inline Skip-Ahead Directives**: Do not add text like *"Non-technical readers: skip ahead to..."* in the section body. The audience badges on the headings are sufficient, and inline directives add unnecessary clutter.

### B. Pure-Technical Tutorials
If a tutorial is designated as technical-only (e.g., advanced API scripting, backend setups):
1. **Omit Audience Badges**: Do not prepend `🟢` or `🔷` to section headings.
2. **Omit Roadmaps**: Do not include the roadmap table unless specifically requested.

---

## 2. Interactive Concept Checks (Quizzes)

To keep lessons interactive, include a quiz at the end of each lesson.

- **Heading**: Use `## 🟢 Concept Check` (or `## Concept Check` in tech-only tutorials).
- **Syntax**: Use GitHub Flavored Markdown (GFM) checkbox task lists:
  - Correct answers must use `* [x]`
  - Incorrect/distractor answers must use `* [ ]`
  - Do NOT use plain bullet points (`* `) or ordered numbers (`1. `) for choices.
- **Renderer Requirement**: The coaching portal parses these checkboxes to generate an interactive quiz interface rather than showing static list items.
