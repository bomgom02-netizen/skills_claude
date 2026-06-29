# Frontend Design Quick Reference

## The One-Sentence Rule
Every design decision should be explainable in one sentence. If you're struggling to explain it, rethink it.

---

## Design Checklist (Pre-Ship)

```
Hero Moment
[ ] Opening element signals what product does
[ ] First impression is distinctive

Color & Contrast
[ ] 4-6 named colors with clear roles
[ ] WCAG AA contrast (4.5:1 for text)
[ ] No pure black or pure white

Typography
[ ] Display, Body, Utility faces chosen intentionally
[ ] Size hierarchy is clear (h1 > h2 > h3 > p)
[ ] Line length comfortable to read

Layout & Spacing
[ ] Grid units applied consistently (4px, 8px, or 16px)
[ ] Whitespace used deliberately
[ ] Alignment creates meaning, not just organization

Interactions
[ ] Transitions are fast (<300ms)
[ ] State changes are clear
[ ] Hover/focus states exist

Copy
[ ] Active voice ("Click here" not "Can be clicked")
[ ] No jargon or assume knowledge
[ ] Concise (cut 20% of words)

Signature Element
[ ] One memorable, distinctive thing
[ ] Couldn't belong to another product
```

---

## Color Palette Template

```
Primary:    [action, emphasis]      #??????
Secondary:  [supporting elements]   #??????
Success:    [positive states]       #??????
Warning:    [caution, attention]    #??????
Neutral:    [backgrounds]           #??????
Text:       [primary content]       #??????
Muted:      [secondary content]     #??????
```

**Naming convention:** Role-based names (Primary, Success) beat appearance-based names (Blue, Green).

---

## Typography Template

```
Display Face:  [Headline face]
               Use: h1, h2, hero moments
               Sizes: 32px–56px
               
Body Face:     [Reading face]
               Use: p, labels, descriptions
               Sizes: 14px–18px
               
Utility Face:  [Code/technical]
               Use: code, pre, terminal
               Sizes: 12px–14px
```

---

## Layout Grid Template

```
Unit Base:      [4px, 8px, or 16px]
Spacing Scale:  Unit × [1, 2, 3, 4, 6, 8, 12, 16...]
Max Width:      [720px, 1024px, 1200px, 1440px]
Breakpoints:    Mobile [320px], Tablet [768px], Desktop [1024px+]
```

---

## Wireframe Template (ASCII Art)

Use this structure for sketching:

```
┌─────────────────────────────────────┐
│  HEADER / NAVIGATION                │
├─────────────────────────────────────┤
│                                     │
│  HERO SECTION                       │
│  [Characteristic opening element]   │
│                                     │
├─────────────────────────────────────┤
│                                     │
│  PRIMARY CONTENT AREA               │
│                                     │
│  Section 1  │  Section 2            │
│             │                        │
├─────────────────────────────────────┤
│  FOOTER / ADDITIONAL INFO           │
└─────────────────────────────────────┘
```

---

## Anti-Pattern Checklist (Things to Avoid)

```
[ ] Generic color schemes (beige + light gray)
[ ] Every element styled the same (no hierarchy)
[ ] Trendy typefaces (chasing fashion)
[ ] Tiny text (under 16px on mobile)
[ ] No whitespace (packed content)
[ ] Auto-playing media (distracting)
[ ] Rainbow color palette (unintentional)
[ ] Misaligned elements (looks broken)
[ ] No micro-interactions (feels dead)
[ ] Copy full of jargon (confusing users)
```

---

## Two-Pass Timeline

### Pass 1: Brainstorm & Plan (15–30 min)
- [ ] Read brief, understand users & context
- [ ] Sketch color palette
- [ ] Choose typography with intent
- [ ] Draw wireframe or ASCII layout
- [ ] Define signature element
- [ ] Critique against brief: Distinctive? Intentional?

### Pass 2: Build & Refine (60–90 min)
- [ ] Set up design tokens
- [ ] Build components to spec
- [ ] Assemble full page/flow
- [ ] Test responsive breakpoints
- [ ] Polish interactions and spacing
- [ ] Accessibility audit (contrast, keyboard, semantics)
- [ ] Final self-critique

---

## Signature Element Ideas

**Visual:**
- Custom illustration style
- Unique color combination
- Distinctive typography treatment
- Memorable icon set

**Structural:**
- Unexpected layout choice
- Non-standard grid
- Unique navigation pattern
- Custom animation

**Experiential:**
- Distinctive interaction pattern
- Unique micro-interaction
- Personality in error states
- Memorable onboarding flow

---

## Common Questions

**Q: How many colors should I use?**  
A: 4–6. Any more becomes a rainbow, any fewer might feel limited.

**Q: Should I use system fonts?**  
A: System fonts are accessible and fast. Use them confidently unless the brief calls for personality.

**Q: What about dark mode?**  
A: Plan it in Pass 1. Invert 1:1 rarely works. Design intentional dark-mode colors.

**Q: How do I know if my design is distinctive?**  
A: Can someone else's product look identical? If yes, it's too generic. Rethink.

**Q: When should I use gradients?**  
A: Rarely. If you must, one gradient max, and it should serve a purpose (hierarchy, energy).

---

## Resources for Designers

- **Color Contrast:** https://webaim.org/resources/contrastchecker/
- **Typography Pairing:** Google Fonts, Typeface, Font Pair
- **Spacing Visualization:** Your browser DevTools (measure pixels)
- **Accessibility:** WCAG 2.1 AA standard (minimum)
- **Motion:** 200–300ms for most transitions, 500ms for major state changes

---

## Remember

> The best designs feel inevitable because they're grounded in something true about their subject.

Design intentionally. Critique ruthlessly. Ship confidently.
