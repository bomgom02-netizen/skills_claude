# Frontend Design Skill

A comprehensive guide to creating distinctive, intentional visual design for web products.

## Overview

This skill provides guidance for designers and developers building new UI or reshaping existing interfaces. It emphasizes:

- **Grounded design** rooted in specific product context
- **Intentional choices** at every level (color, typography, layout)
- **Distinctive personality** rather than templated defaults
- **Two-pass approach** to design planning and implementation

## Files in This Skill

### `SKILL.md` - Core Guidance
The main skill documentation. Read this first. Contains:
- Design approach and principles
- Two-pass design process (brainstorm → build)
- Specific guidance on color, typography, layout
- Design principles (hero, typography, structure, motion, complexity, content)

### `EXAMPLES.md` - Real-World Examples
Four example designs showing the principles in action:
1. Data Visualization Dashboard (real-time market tracking)
2. Educational Course Platform (transformation-focused learning)
3. AI Chatbot Interface (conversational clarity)
4. Premium Analytics Dashboard (serious, professional)

Each example includes:
- The brief (what's this product doing?)
- Design plan (colors, typography, layout, signature element)
- Implementation notes
- Anti-pattern examples (what not to do)

### `QUICK_REFERENCE.md` - At-a-Glance Guide
Condensed version for when you need answers fast:
- One-sentence rule
- Design checklist
- Templates for color, typography, layout
- ASCII wireframe template
- Common questions answered

### `DESIGN_TEMPLATE.md` - Planning Worksheet
Fill-in-the-blank template for **Pass 1** (brainstorm & plan):
- Brief section (what is this product?)
- Design decisions (colors, typography, layout)
- Signature element
- User journey mapping
- Self-critique questions
- Build checklist for Pass 2

## Quick Start

### If You're New to This Skill

1. Read **`SKILL.md`** (10 min)
2. Look at **`EXAMPLES.md`** (5 min)
3. Check out **`QUICK_REFERENCE.md`** for your specific question (2 min)

### If You're Starting a Design Project

1. Read the brief
2. Open **`DESIGN_TEMPLATE.md`** and fill it out (15–30 min for Pass 1)
3. Self-critique using the checklist
4. Build following the template (60–90 min for Pass 2)
5. Ship when you can explain every choice

### If You Need a Quick Answer

Go to **`QUICK_REFERENCE.md`**. Most common questions answered there.

## Key Principles

### The One-Sentence Rule
Every design decision should be explainable in one sentence. If you can't, rethink it.

### Two-Pass Process

**Pass 1: Brainstorm & Plan (15–30 min)**
- Understand the brief and context
- Choose color palette (4–6 colors)
- Select typography (display, body, utility)
- Sketch layout or wireframe
- Define signature element
- Critique: Is this distinctive?

**Pass 2: Build & Refine (60–90 min)**
- Implement design tokens
- Build components to spec
- Assemble full interface
- Test responsive breakpoints
- Polish interactions
- Accessibility audit

### Core Design Principles

1. **Hero as Thesis** - Opening element should signal what the product does
2. **Typography as Personality** - Type carries brand voice and personality
3. **Structure Encodes Meaning** - Layout should communicate, not just organize
4. **Deliberate Motion** - Animation has purpose, never distraction
5. **Complexity Matching Vision** - Visual sophistication matches product sophistication
6. **Intentional Written Content** - Copy is part of design

## Design Tokens

### Color Palette Structure

```
Primary:    [action, emphasis]
Secondary:  [supporting elements]
Success:    [positive states]
Warning:    [caution, errors]
Neutral:    [backgrounds]
Text:       [primary content]
Muted:      [secondary content]
```

**Constraint:** 4–6 named colors maximum. Name them by role, not appearance.

### Typography Structure

```
Display:   Headline & hero font (32px–56px)
Body:      Reading & label font (14px–18px)
Utility:   Code & technical font (12px–14px)
```

### Spacing System

```
Base unit: 4px, 8px, or 16px
Scale:     unit × [1, 2, 3, 4, 6, 8, 12, 16...]
Max width: 720px–1440px (choose your product's width)
```

## Common Anti-Patterns (What to Avoid)

- ❌ Generic defaults (beige backgrounds, system fonts, standard layouts)
- ❌ Trend chasing (designing for trends instead of product)
- ❌ Over-complication (visual noise ≠ sophistication)
- ❌ Ignoring whitespace (packing content, not breathing room)
- ❌ Accessibility as afterthought (should be designed in, not added)
- ❌ Copy as filler (content is part of design)

## Before You Ship

**Design Checklist:**

- [ ] Does the hero moment signal what this product does?
- [ ] Is the color palette limited (4–6 colors) and intentional?
- [ ] Is typography hierarchy clear?
- [ ] Is whitespace used deliberately?
- [ ] Is there one signature element?
- [ ] Do interactions feel responsive?
- [ ] Is copy active, clear, and concise?
- [ ] Sufficient contrast (WCAG AA)?
- [ ] Can I explain every design choice?

If you can't confidently check these boxes, spend 15 more minutes rethinking.

## Pro Tips

1. **Name colors by role, not appearance.** "Primary" beats "Blue."
2. **Whitespace is a design element.** Don't fear empty space.
3. **Limit bold choices to one area.** Bold everywhere = bold nowhere.
4. **Typography is personality.** Choose intentionally.
5. **Interactions should clarify or celebrate.** Never distract.
6. **Constraint creates confidence.** A limited palette looks intentional.
7. **Self-critique throughout.** Ask: "Does this still feel intentional?"

## When to Break the Rules

This skill is guidance, not law. You can break these principles if:

- You can explain why in one sentence
- It serves the brief better
- It doesn't sacrifice accessibility
- You've considered the tradeoff

But if you're breaking rules because you haven't thought through them, rethink instead.

## Questions?

- **Design principles:** See `SKILL.md`
- **Practical examples:** See `EXAMPLES.md`
- **Quick answers:** See `QUICK_REFERENCE.md`
- **Starting a project:** Use `DESIGN_TEMPLATE.md`

---

**Design is done when you can point to every choice and say: "I did this because..."**

Start with intention. Build with confidence. Ship what you own.
