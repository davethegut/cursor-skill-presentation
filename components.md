# Slide Component Library

Pick components based on the content you have. These are building blocks, not a required sequence. Mix and match freely.

---

## 1. Title Slide

Hero opening. One per deck, always first.

```html
<div class="slide active" data-slide="0">
  <div class="slide-inner" style="text-align: center; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 28px;">
    <h1 style="font-size: 3.4rem; max-width: 800px;">
      First Line<br><span class="gradient-text">Emphasized Line</span><br>Third Line
    </h1>
    <p class="lead" style="max-width: 640px;">
      One or two sentences describing the presentation's purpose.
    </p>
    <div style="margin-top: 16px; display: flex; gap: 16px; align-items: center;">
      <span class="tag tag-blue">Tag One</span>
      <span class="tag tag-purple">Tag Two</span>
      <span style="color: var(--text-muted); font-size: 0.85rem;">Date</span>
    </div>
  </div>
</div>
```

**When to use:** Always. Every deck needs a title slide.
**Customize:** Number of lines in h1, tags, optional SVG icon above the title.

---

## 2. Stat Cards

Big numbers or keywords that anchor a point. Use 2-4 cards.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <p style="margin-bottom: 36px; max-width: 750px;">Context paragraph.</p>
    <div class="card-grid card-grid-3">
      <div class="card" style="text-align: center;">
        <div class="stat-value gradient-text">42%</div>
        <div class="stat-label">Description of what this number means</div>
      </div>
      <div class="card" style="text-align: center;">
        <div class="stat-value" style="color: var(--elastic-pink);">$1.2M</div>
        <div class="stat-label">Another metric with context</div>
      </div>
      <div class="card" style="text-align: center;">
        <div class="stat-value" style="color: var(--elastic-teal);">3x</div>
        <div class="stat-label">Third metric with context</div>
      </div>
    </div>
  </div>
</div>
```

**When to use:** You have concrete numbers, percentages, or impactful keywords to anchor.
**Variants:** `card-grid-2`, `card-grid-3`, `card-grid-4`. Use `stat-small` class on `.card` for smaller numbers. Stat values can be numbers, words ("Manual", "Delta"), or short phrases.

---

## 3. Before / After Comparison

Two-column contrast with check/cross icons.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <div class="comparison">
      <div class="comparison-box comparison-before">
        <div class="comparison-label">Before / Problem / Today</div>
        <ul>
          <li>Pain point one</li>
          <li>Pain point two</li>
          <li>Pain point three</li>
        </ul>
      </div>
      <div class="comparison-box comparison-after">
        <div class="comparison-label">After / Solution / Proposed</div>
        <ul>
          <li>Improvement one</li>
          <li>Improvement two</li>
          <li>Improvement three</li>
        </ul>
      </div>
    </div>
    <div class="callout callout-blue">
      <p style="color: var(--text-secondary);">
        <strong style="color: var(--elastic-blue);">Key takeaway.</strong> One sentence summary.
      </p>
    </div>
  </div>
</div>
```

**When to use:** Contrasting current vs. proposed state, old vs. new, problem vs. solution.
**Labels are flexible:** "Today" / "After", "Without" / "With", "Option A" / "Option B", etc.

---

## 4. Pipeline / Flow Diagram

Horizontal stepped flow with arrows. Best for 3-7 steps.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <p style="margin-bottom: 24px;">Brief description of the flow.</p>
    <div class="pipeline">
      <div class="pipeline-step" style="border-left: 3px solid var(--elastic-pink);">
        <div class="step-num">01</div>
        <div class="step-title">Step Name</div>
        <div class="step-detail">Brief detail</div>
      </div>
      <div class="pipeline-arrow">&rarr;</div>
      <div class="pipeline-step" style="border-left: 3px solid var(--elastic-teal);">
        <div class="step-num">02</div>
        <div class="step-title">Step Name</div>
        <div class="step-detail">Brief detail</div>
      </div>
      <div class="pipeline-arrow">&rarr;</div>
      <div class="pipeline-step" style="border-left: 3px solid var(--elastic-blue);">
        <div class="step-num">03</div>
        <div class="step-title">Step Name</div>
        <div class="step-detail">Brief detail</div>
      </div>
    </div>
  </div>
</div>
```

**When to use:** Showing a process, architecture, data flow, workflow, or sequence of steps.
**Collapses vertically** on mobile automatically.

---

## 5. Data Table

Structured rows for detailed comparisons, feature lists, status tracking.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <div class="card">
      <h3 style="font-size: 1rem; color: var(--elastic-teal);">Table Title</h3>
      <table class="data-table">
        <thead><tr><th>Column A</th><th>Column B</th><th>Column C</th></tr></thead>
        <tbody>
          <tr><td class="highlight-cell">Row 1 key</td><td>Detail</td><td>Detail</td></tr>
          <tr><td class="highlight-cell">Row 2 key</td><td>Detail</td><td>Detail</td></tr>
        </tbody>
      </table>
    </div>
  </div>
</div>
```

**When to use:** PRs, issues, feature matrices, metric targets, timelines with details.
**Can stack multiple tables** in one slide (e.g., "Active" and "Completed" sections).

---

## 6. Feature / Ecosystem Grid

Clickable cards in a 2x2 or 2x4 grid. Great for showing related items.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <p style="margin-bottom: 28px;">Context paragraph.</p>
    <div class="card-grid card-grid-2">
      <a href="https://example.com" target="_blank" rel="noopener noreferrer" class="eco-card" style="text-decoration: none;">
        <div class="eco-tag"><span class="tag tag-blue">Category</span></div>
        <div class="eco-title">Item Title</div>
        <div class="eco-how">How it connects / value prop</div>
        <div class="eco-detail">One sentence of additional detail.</div>
      </a>
      <!-- Repeat for each card -->
    </div>
  </div>
</div>
```

**When to use:** Related features, ecosystem connections, team dependencies, resource links.
**Links are optional** — use `<div class="eco-card">` instead of `<a>` for non-clickable cards.

---

## 7. Quote Gallery

Customer quotes, user feedback, stakeholder statements.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <p style="margin-bottom: 24px;">Context about where these quotes come from.</p>
    <div class="card-grid card-grid-2">
      <div class="quote-card">
        <div class="quote-text">The actual quote text goes here.</div>
        <div class="quote-source"><strong>Attribution</strong> &mdash; Source context</div>
      </div>
      <!-- Repeat for each quote -->
    </div>
  </div>
</div>
```

**When to use:** Customer evidence, user research findings, stakeholder endorsements, support case excerpts.
**2-4 quotes per slide** is the sweet spot.

---

## 8. Content Cards with Lists

Cards containing bullet-point lists. Good for feature breakdowns, options, or categorized info.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <p style="margin-bottom: 28px;">Context paragraph.</p>
    <div class="card-grid card-grid-3">
      <div class="card" style="border-top: 3px solid var(--elastic-blue);">
        <h3 style="font-size: 1rem; color: var(--elastic-blue);">Card Title</h3>
        <ul class="card-list">
          <li>Point one</li>
          <li>Point two</li>
          <li>Point three</li>
        </ul>
      </div>
      <!-- Repeat for each card -->
    </div>
  </div>
</div>
```

**When to use:** Comparing options, categorizing features, showing phases or tracks of work.
**Colored top borders** help visually distinguish categories.

---

## 9. Timeline

Vertical timeline for roadmaps, milestones, or chronological events.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <div class="card" style="padding: 32px;">
      <div class="timeline">
        <div class="timeline-item done">
          <div class="timeline-date">Jan 2026</div>
          <div class="timeline-title">Completed milestone</div>
          <div class="timeline-detail">What was delivered</div>
        </div>
        <div class="timeline-item">
          <div class="timeline-date">Mar 2026</div>
          <div class="timeline-title">Current milestone</div>
          <div class="timeline-detail">What's in progress</div>
        </div>
        <div class="timeline-item future">
          <div class="timeline-date">Q2 2026</div>
          <div class="timeline-title">Upcoming milestone</div>
          <div class="timeline-detail">What's planned</div>
        </div>
      </div>
    </div>
  </div>
</div>
```

**When to use:** Roadmaps, delivery plans, project history, release timelines.
**States:** `.done` (teal dot), default (blue dot), `.future` (gray dot).

---

## 10. Two-Column Wrap-Up

Split summary — problem/solution, challenges/wins, key points/next steps.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <div class="wrap-grid">
      <div class="wrap-left">
        <div class="wrap-label">Left Column Label</div>
        <ul class="wrap-list">
          <li>Point one</li>
          <li>Point two</li>
          <li>Point three</li>
        </ul>
      </div>
      <div class="wrap-right">
        <div class="wrap-label">Right Column Label</div>
        <ul class="wrap-list">
          <li>Point one</li>
          <li>Point two</li>
          <li>Point three</li>
        </ul>
      </div>
    </div>
  </div>
</div>
```

**When to use:** Closing slides, executive summaries, any two-perspective summary.
**Column labels are flexible:** Problem/Solution, Challenges/Wins, Risks/Mitigations, etc.

---

## 11. Big Statement Slide

Single powerful statement with optional supporting stats below.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner" style="text-align: center; display: flex; flex-direction: column; align-items: center; justify-content: center;">
    <h2 style="font-size: 2.4rem; max-width: 800px; margin-bottom: 24px;">
      The single most important <span class="gradient-text">takeaway statement</span> of the deck
    </h2>
    <p class="lead" style="max-width: 600px; margin-bottom: 32px;">
      One supporting sentence that reinforces the point.
    </p>
    <div class="card-grid card-grid-4" style="max-width: 800px;">
      <div style="text-align: center;">
        <div style="font-size: 2rem; font-weight: 800; color: var(--elastic-blue);">20+</div>
        <div style="font-size: 0.8rem; color: var(--text-muted);">stat label</div>
      </div>
      <!-- Repeat for supporting stats -->
    </div>
  </div>
</div>
```

**When to use:** The "so what" moment. The ask. The closing punch. Also good for section dividers.
**Supporting stats are optional** — sometimes just the statement is enough.

---

## 12. Narrative Slide

Text-heavy slide for context, background, or explanation. Use sparingly.

```html
<div class="slide" data-slide="N">
  <div class="slide-inner">
    <h2>Slide Title</h2>
    <div style="max-width: 750px;">
      <p style="margin-bottom: 20px;">First paragraph of narrative content. Keep it focused on one idea.</p>
      <p style="margin-bottom: 20px;">Second paragraph if needed. Each paragraph should advance the story.</p>
    </div>
    <div class="callout callout-teal">
      <p style="color: var(--text-secondary);">
        <strong style="color: var(--elastic-teal);">Key insight:</strong> The one thing the audience should take from this slide.
      </p>
    </div>
  </div>
</div>
```

**When to use:** Background context, strategic framing, problem setup. Max 1-2 per deck.
**Always pair with a callout** to anchor the key point — otherwise the audience loses focus.

---

## Utility Elements

These can be added to any slide type:

### Callout (key takeaway)
```html
<div class="callout callout-blue">
  <p style="color: var(--text-secondary);">
    <strong style="color: var(--elastic-blue);">Label:</strong> Message text.
  </p>
</div>
```
Colors: `callout-blue`, `callout-teal`, `callout-pink`, `callout-purple`, `callout-yellow`

### Source Note (attribution)
```html
<div class="source-note">
  Based on data from [source]. Figures as of [date].
</div>
```

### Tags (inline labels)
```html
<span class="tag tag-blue">Label</span>
<span class="tag tag-teal">Label</span>
<span class="tag tag-pink">Label</span>
<span class="tag tag-purple">Label</span>
<span class="tag tag-yellow">Label</span>
```

### Footer / Attribution Line
```html
<div style="text-align: center; margin-top: 24px; color: var(--text-muted); font-size: 0.85rem;">
  Author Name &middot; Role &middot; Date &middot; <a href="URL" style="color: var(--elastic-blue);">Link</a>
</div>
```
