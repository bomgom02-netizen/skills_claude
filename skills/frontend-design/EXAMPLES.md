# Frontend Design Skill Examples

## Example 1: Data Visualization Dashboard

### Brief
A dashboard for traders to track real-time market data with quick decision-making.

### Design Plan

**Color Palette:**
```
Primary:    #1e293b (charts, key metrics)
Success:    #10b981 (gains, up trends)
Warning:    #f59e0b (losses, down trends)
Background: #0f172a (dark theme for long viewing)
Text:       #e2e8f0 (light text on dark)
```

**Typography:**
```
Display: Space Mono (monospace, technical feel)
Body:    Inter (clean, modern, readable)
Utility: JetBrains Mono (for code/technical values)
```

**Layout:**
- Grid: 8px units
- Max width: 1440px (wide for charts)
- Key section at top: Quick summary cards
- Charts fill remaining space with intentional rhythm

**Signature Element:**
- Micro-animations: Charts animate on load, data updates trigger smooth transitions
- Creates feeling of live data without being disruptive

### Implementation Notes
- Use color to encode data meaning (green up, red down) but maintain enough contrast
- Typography hierarchy: Metric names small and muted, values large and primary
- Whitespace around chart areas—they need breathing room

---

## Example 2: Educational Course Platform

### Brief
A learning platform for busy professionals. Hero moment: Show transformation (before/after learner journey).

### Design Plan

**Color Palette:**
```
Primary:    #6366f1 (CTAs, progress indicators)
Secondary:  #06b6d4 (complementary interactive elements)
Success:    #22c55e (completed lessons, achievements)
Neutral:    #f8fafc (card backgrounds)
Text:       #1e293b (readable dark text)
```

**Typography:**
```
Display: Outfit (friendly, modern, approachable)
Body:    System stack (accessible, fast)
Utility: Mono (for code examples within courses)
```

**Layout:**
- Grid: 16px units
- Max width: 1024px (focuses on content)
- Left sidebar for navigation (persistent on desktop)
- Course progress as central visual element

**Signature Element:**
- Progress visualization: Custom progress ring showing completion, not just a bar
- Hand-drawn illustrations for course categories (adds personality)

### Implementation Notes
- Course cards should feel like invitations, not assignments
- Progress should celebrate incremental wins
- Typography size should adjust gracefully (mobile: 16px base, desktop: 18px base)

---

## Example 3: AI Chatbot Interface

### Brief
Conversational AI assistant. Hero moment: Make it clear you're talking to something helpful, not human.

### Design Plan

**Color Palette:**
```
Primary:    #3b82f6 (user messages)
Secondary:  #8b5cf6 (assistant responses)
Neutral:    #f3f4f6 (backgrounds)
Text:       #111827 (high contrast)
Accent:     #ec4899 (actions, generating state)
```

**Typography:**
```
Display: Poppins (friendly, modern)
Body:    Segoe UI / -apple-system (accessible, natural)
Utility: Source Code Pro (code blocks in responses)
```

**Layout:**
- Grid: 4px units (fine-grained control)
- Full height conversation area
- Input at bottom (sticky on scroll)
- Message bubbles with clear side differentiation

**Signature Element:**
- Animated typing indicator (pulsing dots showing thinking)
- Message entrance animation (subtle slide + fade)

### Implementation Notes
- Message bubbles should have clear ownership (user vs. assistant)
- Code blocks within messages should be copyable and syntax-highlighted
- Loading states should feel thoughtful (typing animation, not just spinner)

---

## Example 4: Analytics Dashboard (Minimal, Premium)

### Brief
Premium analytics for professionals. Hero moment: High-level KPI visibility.

### Design Plan

**Color Palette:**
```
Primary:    #2d3748 (dark, serious, premium)
Accent:     #48bb78 (metrics, emphasis)
Neutral:    #ffffff (cards, clarity)
Text:       #2d3748 (high contrast)
Muted:      #a0aec0 (secondary info)
```

**Typography:**
```
Display: IBM Plex Serif (serious, trustworthy)
Body:    IBM Plex Sans (professional, clean)
Utility: IBM Plex Mono (data, code)
```

**Layout:**
- Grid: 16px units
- Max width: 1400px
- Top-level metrics in fixed header
- Detailed view below (scrollable)
- Heavy use of whitespace around numbers

**Signature Element:**
- Premium card design: Subtle shadow, generous padding, premium typeface
- Data visualization: Custom color themes that feel cohesive

### Implementation Notes
- Numbers should breathe (lots of whitespace around large figures)
- Trends should be shown simply (arrow + percentage, not complex chart)
- Typography should convey authority, not friendliness

---

## Design Anti-Pattern Examples

### ❌ Generic Dashboard (What Not to Do)
- Light gray background + white cards (templated)
- Random colors for data (red/blue for arbitrary distinction)
- Small text, dense layout
- No visual personality

### ✅ Intentional Dashboard (Better Approach)
- Meaningful color (green for revenue, blue for engagement)
- Strategic whitespace around key metrics
- Typography hierarchy (large numbers, small labels)
- One signature detail (custom chart style or unique layout choice)

---

## Applying the Two-Pass Process

### Pass 1: Plan (15-30 min)
1. Read the brief carefully
2. Sketch or describe color palette (3-5 colors with roles)
3. List typography choices and their purposes
4. Draw ASCII wireframe or written layout description
5. Identify signature element
6. Ask: Does this feel distinctive? Not templated?

### Pass 2: Build (60-90 min)
1. Set up design tokens (colors, spacing, typography)
2. Build components following the plan
3. Assemble full page/flow
4. Self-critique: Does it still feel intentional?
5. Polish interactions and spacing
6. Check accessibility (contrast, readability)

---

## Critique Questions

When reviewing your own work:

- **Grounded?** Does this design make sense for this specific product?
- **Distinctive?** Would someone recognize this as uniquely this product?
- **Intentional?** Can I explain every design choice in one sentence?
- **Restrained?** Are bold choices in one place, not everywhere?
- **Readable?** Can a user understand the hierarchy without effort?
- **Responsive?** Does it work at all breakpoints?
- **Accessible?** Sufficient contrast? Keyboard navigable? Understandable?

Most of the time, if you're asking these questions, you're on the right track.
