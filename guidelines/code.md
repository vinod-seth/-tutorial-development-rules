# Portal Frontend Coding Guidelines

These guidelines define how the portal frontend (specifically `MarkdownRenderer.tsx` and related components) must parse and display custom tutorial markdown elements.

---

## 1. HTML Details/Summary Parsing

The frontend must natively support collapsible details blocks to enable click-to-reveal components.

- **Component Mapping**: Inside the markdown parser (`ReactMarkdown` or similar), map `details` and `summary` HTML elements to styled react components (e.g. `CollapsibleDetails`).
- **Styling**: Ensure smooth transition animations, clean margins, and distinct cursor-pointer styles on the summary block.

---

## 2. Interactive Quiz Integration

Instead of rendering standard checkbox inputs for quiz task items, the renderer must dynamically parse quizzes.

- **Intersection Rule**: List items matching the pattern `* [ ]` or `* [x]` that appear inside the `Concept Check` section must be parsed as interactive quiz options.
- **State Management**:
  - The options should support user selection.
  - Selecting the correct option (`* [x]`) must show a success banner with a reward/motivational message.
  - Selecting an incorrect option (`* [ ]`) must show a warning banner suggesting the user click the "Click to Reveal" helper or try again.
  - Selection states must reset/retry cleanly.
