# Tutorial Rendering & UX Guidelines

These guidelines specify how to write UI/UX layout constructs (e.g. collapsible answers, tables) in the tutorial files.

---

## 1. Click-to-Reveal Answer & Explanations

To ensure answers and detailed explanations do not spoil the exercise or quiz immediately, they must be hidden by default.

- **Tag Wrapper**: Wrap the answer and explanation in standard HTML `<details>` and `<summary>` tags.
- **Summary Header**: The `<summary>` text must start with the key icon: `🔑 Click to Reveal Answer & Explanation`.
- **Formatting**: Keep markdown content inside the `<details>` tag formatted properly. Use blank lines around markdown headers or paragraphs inside the HTML tag to ensure proper rendering.

*Example:*
```html
<details>
<summary>🔑 Click to Reveal Answer & Explanation</summary>

The correct answer is **B**. 

Here is why:
- Option A is incorrect because...
- Option B is correct because...
</details>
```

---

## 2. Tables Inside Blockquotes (e.g. Roadmaps)

When nesting markdown tables inside blockquotes (`> `), follow these parsing rules:

- **Empty Line Separation**: Always separate the blockquote intro text from the table header with a blockquote-prefixed blank line (`> `).
- **Line Prefixes**: Place the blockquote symbol `>` at the beginning of every line (including empty lines and table rows).

*Example:*
```markdown
> **📍 Lesson Roadmap:**
> 
> | Section | Audience |
> |:---|:---|
> | 1. Introduction | 🟢 Everyone |
```
