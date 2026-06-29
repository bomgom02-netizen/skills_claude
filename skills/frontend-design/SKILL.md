# Frontend Design Skill

**name:** frontend-design  
**description:** Guidance for distinctive, intentional visual design when building new UI or reshaping an existing one

## Approach

Design as a distinctive studio lead, not using templated defaults. The goal is to create designs that are intentional, grounded in the product's specific context, and memorable—not generic AI-generated defaults.

When building or reshaping UI, you're not applying a template. You're making deliberate choices about every visual element to serve the product's unique purpose and audience.

## Ground It in the Subject

Anchor design in the product's specific context and vernacular. Before you start sketching:

- **Understand the domain**: What is this product actually doing? What problems does it solve? What community uses it?
- **Learn the language**: What visual or linguistic patterns already exist in this space? What would feel native to users familiar with this domain?
- **Find the insight**: What single thing could make this product distinctive? Usually it's something small and specific to the brief, not a broad design trend.

The strongest designs feel inevitable because they're grounded in something true about their subject.

## Design Principles

### Hero as Thesis
Start with a characteristic opening element—something that immediately signals what this product is about. It doesn't have to be flashy; it has to be honest.

Examples:
- A carefully chosen image that represents the core insight
- A distinctive headline in a unique typographic treatment
- An interaction that demonstrates the core value in 3 seconds
- A structural choice (layout, color, component arrangement) that's unexpected but makes sense

### Typography as Personality Carrier
Type is usually the most visible design decision. Choose with intention:

- **Display face**: Use sparingly for headlines or hero moments. Should feel connected to the product's character
- **Body face**: Readability and personality both matter. Plain doesn't mean boring
- **Utility face**: Monospace for code/technical context, if needed

Don't pick type from trends. Pick type that fits the product's voice.

### Structure Encoding Information
Layout should communicate meaning, not just organize content:

- **Hierarchy**: Use size, color, and position to show what matters most
- **Proximity**: Group related content; separate different concepts
- **Alignment**: Consistency builds confidence; unexpected alignment can signal importance
- **Whitespace**: Space is a design element, not empty area

### Deliberate Motion
Use motion to clarify or celebrate, never to distract:

- Transitions should feel responsive (fast enough to feel instant)
- Animations should have purpose (loading states, state changes, confirmation)
- Never auto-play video or infinite loops that distract from content

### Complexity Matching Vision
A simple product should have simple visual design. A complex product needs visual hierarchy that reveals complexity gradually.

Don't oversimplify. Don't add false visual complexity. Match the visual sophistication to the product's actual sophistication.

### Intentional Written Content
Copy is part of design:

- **Active voice**: "Share your findings" not "findings can be shared"
- **Clarity first**: If a user has to read it twice, rewrite it
- **Personality**: The tone should match the brand's voice
- **Concise**: Every word should earn its place

## Design Process: Two-Pass Approach

### Pass 1: Brainstorm & Plan
Before writing code, spend 15–30 minutes on the design plan:

1. **Define the brief**: What is the core purpose? Who uses it? What moment matters most?
2. **Choose constraints**: 
   - Color palette (4–6 named hex values)
   - Typography (which faces, applied where)
   - Layout principle (grid size, key measurements)
   - One signature element (what will make this design memorable)
3. **Sketch or wireframe**: Use ASCII art, rough sketches, or description. Something concrete enough to critique.
4. **Self-critique against brief**: Does this design prove the thesis? Is it distinctive? Could someone confuse it with a template?

### Pass 2: Build & Refine
As you implement in code:

1. **Follow the plan**: Implement the decisions you made. Don't improvise mid-build.
2. **Self-critique in context**: As components come together, ask: Does this still feel intentional? Does it still serve the brief?
3. **Adjust strategically**: If something isn't working, figure out why (wrong color, wrong rhythm, wrong sizing) and fix the root cause, not just the symptom.
4. **Quality floor**: Ensure consistency, spacing is intentional, interactions respond smoothly.

## Restraint & Self-Critique

You don't need to make everything bold. Bold in one place (the hero, the signature element) creates contrast and impact. Everywhere bold = nowhere bold.

Maintain a quality floor:
- Alignment and spacing should be consistent
- Typography should be readable at every size
- Colors should have contrast
- Interactions should feel responsive

The best designs feel effortless. That effortlessness comes from careful constraint and repeated critique.

## Color: Intentional Palettes

Create a named, limited palette:

```
Primary:     #2563eb (action, emphasis)
Secondary:   #64748b (supporting elements)
Accent:      #f97316 (highlights, celebrations)
Neutral:     #f1f5f9 (backgrounds)
Text:        #0f172a (primary content)
Muted:       #94a3b8 (secondary content)
```

**Why name them?** Because "use the accent color here" is clearer than "use #f97316". Name each color for its role, not its appearance.

Rules:
- No pure black or pure white (they feel harsh)
- Enough contrast for accessibility
- Color should reinforce hierarchy, not fight it

## Typography: Three-Tier System

Most products need exactly three typeface scales:

```
Display:  Headlines & hero moments
          Large, distinctive, breathing room
          
Body:     Paragraph text, UI labels, descriptions
          Comfortable to read, personality without strain
          
Utility:  Code blocks, technical content
          Monospace, clarity over personality
```

Map them clearly:

```
h1, h2:         Display face
h3, p, label:   Body face
code, pre:      Utility face
```

## Layout: Grid & Rhythm

Establish one grid measurement. Common: 4px, 8px, or 16px units.

```
Spacing scale:  4, 8, 12, 16, 24, 32, 48, 64...
Max width:      1200px (or document the choice)
Breakpoints:    Mobile (320px), tablet (768px), desktop (1200px)
                (or whatever fits your product)
```

Use these consistently. When spacing looks off, it's usually because you deviated from the scale.

## Signature Element: The Memorable Detail

Every strong design has one thing that couldn't belong to another product:

- A unique illustration style
- A specific interaction pattern
- A color used in an unexpected place
- A typographic treatment
- A layout quirk that makes sense for this product

It doesn't have to be loud. It has to be unmistakably *this* product.

---

## Process Checklist

Before shipping:

- [ ] Is the design grounded in the product's subject?
- [ ] Does the hero moment communicate the thesis immediately?
- [ ] Is typography applied consistently and strategically?
- [ ] Is the color palette limited and intentional?
- [ ] Is whitespace used deliberately?
- [ ] Is there one signature element that feels distinctive?
- [ ] Do interactions feel responsive and purposeful?
- [ ] Is copy active, clear, and concise?
- [ ] Do I feel ownership of this design, or does it feel templated?

If you can't say yes to most of these, go back to Pass 1 and rethink.

---

## Anti-Patterns to Avoid

**Generic defaults**: Beige backgrounds, system fonts, standard layouts. Question every choice.

**Trend chasing**: Trends are fast-moving. Grounded design lasts longer.

**Over-complication**: Visual noise doesn't equal sophistication. Simplicity with intention beats complexity without purpose.

**Ignoring whitespace**: Whitespace is expensive; use it as a design tool.

**Accessibility as afterthought**: Contrast, readability, and motion should be designed in, not added at the end.

**Copy as filler**: Content is design. Treat it that way.

---

## References

- **Design Thinking**: Frame problems, not just pixels
- **Typography**: Letters are shapes; treat them as design elements
- **Color Science**: Understand contrast, harmony, and meaning
- **Interaction Design**: Every motion should communicate something
- **Accessibility**: Good design is inclusive design

When in doubt: Is this choice intentional? Does it serve the brief? Can I explain why this is better than an alternative? If yes, ship it. If no, rethink.
