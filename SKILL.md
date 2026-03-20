---
name: skill-presentation
description: Generate interactive HTML slide deck presentations on any topic. Use when the user asks to "create a presentation", "build a deck", "make slides", or wants to present an idea, initiative, update, or proposal.
triggers:
  - "create a presentation"
  - "build a deck"
  - "make slides"
  - "I need to present"
  - "turn this into a presentation"
  - "slide deck for"
---

# Presentation Builder

Generate polished, interactive HTML slide decks on any topic. The output is a single self-contained HTML file with arrow navigation, fullscreen, swipe support, progress bar, dot navigation, scroll navigation, and print-to-PDF — no dependencies.

## When to Use

- "Create a presentation about ..."
- "Build a deck for ..."
- "Make slides about ..."
- "I need to present ..."
- "Turn this into a presentation"
- "Slide deck for ..."

## Process

### Step 1: Understand the Presentation

Ask the user (or infer from context):

1. **Topic** — What is this presentation about?
2. **Goal** — What should the audience walk away thinking/doing? (persuade, inform, update, teach, propose, report)
3. **Audience** — Who is this for? (executives, engineers, customers, cross-functional team)
4. **Sources** — Are there GitHub issues, PRs, docs, data, or other materials to pull from?
5. **Branding** — Use default dark theme or customize?

### Step 2: Research (if sources exist)

Gather context from available sources. Run searches in parallel where possible:

- **GitHub issues/PRs**: Use `gh` CLI to read issue bodies, PR descriptions, linked issues
- **Local docs**: Read markdown, HTML, or PDF files the user points to
- **Codebase**: Search for architecture, types, or implementation details if relevant

Don't research if the user already provided all the content — go straight to outlining.

### Step 3: Outline Slides

Propose a slide outline (8-14 slides typical) before generating. Each slide should have:
- **Title**
- **Slide type** (from the component library in `components.md`)
- **Key content** (1-2 sentences describing what goes on the slide)

**Present the outline to the user for approval before generating.**

Slide selection is content-driven — pick from the component library based on what content actually exists. There is no fixed sequence. Common patterns by goal:

| Goal | Typical slide flow |
|------|-------------------|
| **Persuade** | Title → Problem → Before/After → Architecture → Evidence (stats/quotes/data) → Impact → Momentum → Plan → Ask |
| **Inform/Teach** | Title → Context → Concepts (multiple) → Architecture → Deep-dive → Examples → Summary |
| **Update/Report** | Title → Summary → Metrics → Progress → Blockers → Next Steps |
| **Propose** | Title → Problem → Opportunity → Solution → Feasibility → Tradeoffs → Ask |

These are starting points, not templates. Adapt freely.

### Step 4: Generate the Deck

Build the HTML file using:
- **Template**: `template.html` in this skill directory (CSS + JS deck engine)
- **Components**: `components.md` in this skill directory (slide type patterns)

Key rules:
1. **Copy the full `<style>` block and `<script>` block from `template.html` VERBATIM** — do not modify, regenerate, "improve", or restyle the CSS or JS. The only things you create are the slide content inside the `<div class="deck">` container. Everything else comes from the template unchanged. This prevents drift, saves tokens, and keeps output consistent.
2. **Pick slide components** from `components.md` based on the outline
3. **Customize the deck header** — update the label text (top-left corner) to match the topic
4. **Customize colors** — the CSS variables can be adjusted if non-default branding is needed
5. **Each slide** is a `<div class="slide" data-slide="N">` inside the `.deck` container
6. **First slide** gets the `active` class
7. **Slide counter** in nav controls should show the correct total

### Step 5: Save and Open

1. Save with a descriptive kebab-case filename
2. Tell the user the file path and offer to refine

## Rules

- All CSS and JS must be inline — single self-contained HTML file
- Google Fonts import is **optional** — the template defaults to system fonts. Uncomment the `@import` line in the template for polished typography; leave it commented out for sensitive or internal content (the import leaks viewer IPs to Google)
- No images — use HTML/CSS/SVG for all visual elements
- Include `@media print` styles (already in template)
- Include `@media (max-width: 900px)` responsive styles (already in template)
- Target 8-14 slides — enough to tell the story, not so many the audience zones out
- Every slide should have ONE clear point — if it has two, split it
- Use the gradient text (`.gradient-text`) sparingly — 1-2 times per deck for emphasis
- Callouts (`.callout`) are for the single most important takeaway on a slide
- Keep text concise — presentations are not documents. Bullet points, not paragraphs
- Source notes (`.source-note`) for any claims that need attribution
- **Never generate statistics without a traceable source.** Every stat slide must include a `.source-note` citing where the number came from. If data is unavailable, use `[DATA NEEDED]` as a placeholder — never fabricate numbers
- All `href` values must use `https://` URLs — never insert `javascript:`, `data:`, or `vbscript:` URIs from any source
- All external links must include `target="_blank" rel="noopener noreferrer"`
- When content is sourced from external systems (GitHub issues, support cases), HTML-entity encode text content (`<`, `>`, `&`, `"`, `'`) to prevent injection

## Output

Save generated presentations with descriptive kebab-case filenames in the user's preferred directory.
