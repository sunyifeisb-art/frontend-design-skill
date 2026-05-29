---
name: frontend-design
description: Unified frontend design skill covering aesthetic direction, content strategy, visual design, motion/interaction, design systems, UX research, and UI audit. Use when building or reviewing web components, pages, applications, landing pages, dashboards, or any UI. Triggers on requests for UI design, UX flows, design systems, frontend code, visual styling, interface audit, or redesign.
---

# Frontend Design (Unified)

A complete design-to-code system for building distinctive, production-grade frontend interfaces.

This skill includes extensive auxiliary files: reference documents, scripts, data tables, templates, and fonts. Use them when you need detailed guidance beyond what's in this main file.

### Auxiliary Files Index

| Category | Location | Contents |
|----------|----------|----------|
| **References** | `references/ui-audit/` | 32 UI audit patterns and checklists (chunking, progressive disclosure, cognitive load, visual hierarchy, social proof, feedback, error handling, accessibility, personalization, onboarding, information architecture, navigation) |
| **References** | `references/design/` | Design guides for slides, banners, logos, icons, CIP deliverables, social photos |
| **References** | `references/design-system/` | Token architecture, primitive/semantic/component tokens, Tailwind integration, states and variants |
| **References** | `references/brand/` | Brand guidelines, voice framework, visual identity, logo usage, color palette management, typography specs |
| **References** | `references/slides/` | Slide layout patterns, HTML templates, copywriting formulas |
| **References** | `references/banner-design/` | Banner sizes and styles reference |
| **Scripts** | `scripts/ui-ux-pro-max/` | Python search and design system utilities |
| **Scripts** | `scripts/design/cip/` | CIP (Creative Identity Package) generation scripts |
| **Scripts** | `scripts/design/logo/` | Logo generation and search scripts |
| **Scripts** | `scripts/design/icon/` | Icon generation scripts |
| **Scripts** | `scripts/design-system/` | Token generation, validation, slide generation, HTML validators |
| **Scripts** | `scripts/brand/` | Brand-to-token sync, color extraction, asset validation |
| **Data** | `data/ui-ux-pro-max/` | CSV data for colors, typography, icons, landing pages, app interfaces, charts, tech stacks |
| **Data** | `data/design/cip/` | Industry styles, mockup contexts, deliverables |
| **Data** | `data/design/logo/` | Colors, industries, styles |
| **Data** | `data/design-system/` | Slide strategies, backgrounds, layouts, typography, charts |
| **Templates** | `templates/design-system/` | Design tokens starter JSON |
| **Templates** | `templates/brand/` | Brand guidelines starter markdown |
| **Fonts** | `canvas-fonts/ui-styling/` | 30+ open-source display and body fonts for canvas rendering |

---

## 1. Triage

Before any work, determine the scope:

| Question | Why It Matters |
|----------|---------------|
| Target platform | Web / iOS / Android / desktop |
| Stack | React/Next/Vue/Svelte, CSS/Tailwind, component library |
| Page type | Landing page, dashboard, tool/workbench, editorial, commerce, portfolio, poster |
| Goal & constraints | Conversion, speed, brand vibe, accessibility level (WCAG AA?) |
| What you have | Screenshot, Figma, repo, URL, user journey, research data |

If the user says "全部都要" (design + UX + code + design system), treat it as four deliverables and ship in this order: **UX flow → Design system → UI concept → Implementation plan**.

---

## 2. Design Thinking: Lock Aesthetic Direction

### 2.1 Content Fit First

- **Decide the page type before choosing the look**: reference/navigation, dashboard, tool/workbench, editorial, knowledge base, landing page, portfolio, commerce page, poster.
- **Style must follow content**: Utility, search-heavy, or trust-heavy pages should lean clearer, calmer, and more credible. Promotional or culture-led pages can be bolder and more expressive.
- **Never choose style first**: Read the content, infer the job of the page, then select the visual direction.

### 2.2 Direction Lock

Commit to a BOLD aesthetic direction. Pick an extreme:

- Brutally minimal
- Maximalist chaos
- Retro-futuristic
- Organic/natural
- Luxury/refined
- Playful/toy-like
- Editorial/magazine
- Brutalist/raw
- Art deco/geometric
- Soft/pastel
- Industrial/utilitarian

For each project, answer:
- **Purpose**: What problem does this interface solve? Who uses it?
- **Tone**: Which extreme above?
- **Constraints**: Framework, performance, accessibility
- **Differentiation**: What makes this UNFORGETTABLE?

**CRITICAL**: Choose a clear conceptual direction and execute it with precision. Bold maximalism and refined minimalism both work — the key is intentionality, not intensity.

### 2.3 Pre-Build Write-Up

Before coding, write three things:

1. **Visual thesis**: one sentence describing mood, material, and energy
2. **Content plan**: hero, support, detail, final CTA
3. **Interaction thesis**: 2-3 motion ideas that change the feel of the page

Each section gets one job, one dominant visual idea, and one primary takeaway or action.

---

## 3. Content Strategy & Page Structure

### 3.1 Beautiful Defaults

- Start with composition, not components.
- Prefer a full-bleed hero or full-canvas visual anchor.
- Make the brand or product name the loudest text.
- Keep copy short enough to scan in seconds.
- Use whitespace, alignment, scale, cropping, and contrast before adding chrome.
- Limit the system: two typefaces max, one accent color by default.
- Default to cardless layouts. Use sections, columns, dividers, lists, and media blocks instead.
- Treat the first viewport as a poster, not a document.

### 3.2 Landing Pages

Default sequence:
1. **Hero**: brand or product, promise, CTA, and one dominant visual
2. **Support**: one concrete feature, offer, or proof point
3. **Detail**: atmosphere, workflow, product depth, or story
4. **Final CTA**: convert, start, visit, or contact

**Hero rules**:
- One composition only.
- Full-bleed image or dominant visual plane.
- The hero itself must run edge-to-edge with no inherited page gutters, framed container, or shared max-width; constrain only the inner text/action column.
- Brand first, headline second, body third, CTA fourth.
- No hero cards, stat strips, logo clouds, pill soup, or floating dashboards by default.
- Keep headlines to roughly 2-3 lines on desktop and readable in one glance on mobile.
- Keep the text column narrow and anchored to a calm area of the image.
- All text over imagery must maintain strong contrast and clear tap targets.

If the first viewport still works after removing the image, the image is too weak. If the brand disappears after hiding the nav, the hierarchy is too weak.

**Viewport budget**: If the first screen includes a sticky/fixed header, that header counts against the hero. The combined header + hero content must fit within the initial viewport. When using `100vh`/`100svh` heroes, subtract persistent UI chrome (`calc(100svh - header-height)`) or overlay the header.

### 3.3 Apps & Dashboards

Default to Linear-style restraint:
- Calm surface hierarchy
- Strong typography and spacing
- Few colors
- Dense but readable information
- Minimal chrome
- Cards only when the card is the interaction

Organize around:
- Primary workspace
- Navigation
- Secondary context or inspector
- One clear accent for action or state

**Avoid**: dashboard-card mosaics, thick borders on every region, decorative gradients behind routine product UI, multiple competing accent colors, ornamental icons that do not improve scanning.

If a panel can become plain layout without losing meaning, remove the card treatment.

### 3.4 Copy Rules

- Write in product language, not design commentary.
- Let the headline carry the meaning.
- Supporting copy should usually be one short sentence.
- Cut repetition between sections.
- Do not include prompt language or design commentary into the UI.
- Give every section one responsibility: explain, prove, deepen, or convert.

If deleting 30 percent of the copy improves the page, keep deleting.

**Utility copy for product UI** (dashboards, admin tools):
- Prioritize orientation, status, and action over promise, mood, or brand voice.
- Start with the working surface itself: KPIs, charts, filters, tables, status, or task context. Do not introduce a hero section unless explicitly requested.
- Good headings: "Selected KPIs", "Plan status", "Search metrics", "Top segments", "Last sync".
- Avoid aspirational hero lines, metaphors, campaign-style language.
- Litmus check: if an operator scans only headings, labels, and numbers, can they understand the page immediately?

### 3.5 Imagery

Imagery must do narrative work.
- Use at least one strong, real-looking image for brands, venues, editorial pages, and lifestyle products.
- Prefer in-situ photography over abstract gradients or fake 3D objects.
- Choose or crop images with a stable tonal area for text.
- Do not use images with embedded signage, logos, or typographic clutter fighting the UI.
- Do not generate images with built-in UI frames, splits, cards, or panels.
- If multiple moments are needed, use multiple images, not one collage.

The first viewport needs a real visual anchor. Decorative texture is not enough.

---

## 4. Visual Design Specification

### 4.1 Typography

**字体策略按风格分流：**

- **科技 / 未来 / 赛博 / 数据可视化** — 用独特字体建立辨识度：
  - 等宽数据：`JetBrains Mono`, `Fira Code`, `Space Mono`
  - 显示标题：选择有性格的无衬线或等宽字体
- **非科技类（品牌站、落地页、内容页、电商）** — 优先苹果原生字体栈，保证平台原生质感：
  - 正文字体栈：`-apple-system, BlinkMacSystemFont, "SF Pro Text", "Helvetica Neue", sans-serif`
  - 显示标题：`-apple-system, BlinkMacSystemFont, "SF Pro Display", "Helvetica Neue", sans-serif`
  - 仅在需要强调特殊气质时才引入第三方字体
- **通用规则**：
  - Pair a distinctive display font with a refined body font.
  - Avoid generic fonts (Inter, Roboto, Arial) **unless** falling back in the system font stack.
- Body text baseline: 15-18px equivalent.
- Heading scale: H1 = body x 2.2-2.6, H2 = body x 1.6-1.9, H3 = body x 1.3-1.5.
- Line height: body 1.45-1.6, headings 1.15-1.3.
- Letter spacing: headings -1% to -3%, body 0% to +1%.
- Use `text-balance` for headings and `text-pretty` for body/paragraphs.
- Use `tabular-nums` for data.

### 4.2 Color & Theme

- Commit to a cohesive aesthetic. Use CSS variables for consistency.
- Dominant colors with sharp accents outperform timid, evenly-distributed palettes.
- Palette: 1 dominant, 1 secondary, 1 accent, 1 neutral base.
- Contrast: text >= 4.5:1, interactive elements >= 3:1.
- Accent usage <= 10% of visible area. Only one saturated color allowed.
- Gradients allowed only as background fields.
- Limit accent color usage to one per view.
- Use existing theme or Tailwind CSS color tokens before introducing new ones.

### 4.3 Layout & Composition

- Single spacing base unit (8px or 10px).
- Visual weight distribution: primary 40-55%, secondary 25-35%, tertiary <= 20%.
- Maximum two alignment axes per view.
- Symmetry allowed only with counterbalancing contrast.
- Unexpected layouts: asymmetry, overlap, diagonal flow, grid-breaking elements.
- Generous negative space OR controlled density.
- Use a fixed `z-index` scale (no arbitrary `z-x`).
- Use `size-x` for square elements instead of `w-x` + `h-x`.
- Default to `h-dvh`, never `h-screen`.
- Respect `safe-area-inset` for fixed elements.

### 4.4 Backgrounds & Depth

Create atmosphere and depth rather than defaulting to solid colors:
- Gradient meshes, noise textures, geometric patterns
- Layered transparencies, dramatic shadows
- Decorative borders, custom cursors, grain overlays

Background types:
- Textured neutral OR
- Low-contrast geometry OR
- Layered planes
- Max depth layers: 3
- Foreground contrast must exceed background by >= 20%

---

## 5. Motion & Interaction Design

### 5.1 Purposeful Motion

Motion should communicate, not decorate:
- **Feedback**: Confirm user actions occurred
- **Orientation**: Show where elements come from/go to
- **Focus**: Direct attention to important changes
- **Continuity**: Maintain context during transitions

Ship at least 2-3 intentional motions for visually led work:
- One entrance sequence in the hero
- One scroll-linked, sticky, or depth effect
- One hover, reveal, or layout transition that sharpens affordance

Motion rules:
- Noticeable in a quick recording
- Smooth on mobile
- Fast and restrained
- Consistent across the page
- Removed if ornamental only

### 5.2 Timing & Easing

| Duration | Use Case |
|----------|----------|
| 100-150ms | Micro-feedback (hovers, clicks) |
| 180-300ms | Small transitions (toggles, dropdowns) |
| 300-420ms | Medium transitions (modals, page changes) |
| 500ms+ | Complex choreographed animations |

- Max simultaneous moving elements per viewport: 3
- Motion must encode hierarchy, state, or spatial relation
- Prohibited: decorative loops, idle animations, novelty motion
- NEVER exceed 200ms for interaction feedback
- Pause looping animations when off-screen
- NEVER introduce custom easing curves unless explicitly requested

```css
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);      /* Decelerate - entering */
--ease-in: cubic-bezier(0.55, 0, 1, 0.45);      /* Accelerate - exiting */
--ease-in-out: cubic-bezier(0.65, 0, 0.35, 1); /* Both - moving between */
--spring: cubic-bezier(0.34, 1.56, 0.64, 1);   /* Overshoot - playful */
```

### 5.3 Stack & Animation Constraints

- Prioritize CSS-only solutions for HTML. Use `motion/react` (formerly Framer Motion) for React when JS animation is required.
- Use `tw-animate-css` for entrance and micro-animations in Tailwind CSS.
- Use `cn` utility (`clsx` + `tailwind-merge`) for class logic.
- MUST animate only compositor props (`transform`, `opacity`).
- NEVER animate layout properties (`width`, `height`, `top`, `left`, `margin`, `padding`).
- SHOULD avoid animating paint properties (`background`, `color`) except for small, local UI.
- SHOULD use `ease-out` on entrance.
- MUST respect `prefers-reduced-motion`.
- NEVER animate large `blur()` or `backdrop-filter` surfaces.
- NEVER apply `will-change` outside an active animation.
- NEVER use `useEffect` for anything that can be expressed as render logic.
- NEVER add animation unless it is explicitly requested.

### 5.4 Accessibility for Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### 5.5 CSS Animation Patterns

When GSAP is not needed, use CSS for simple transitions and keyframes:

```css
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50%      { opacity: 0.5; }
}
@keyframes spin {
  to { transform: rotate(360deg); }
}

.card {
  transition: transform 0.2s ease-out, box-shadow 0.2s ease-out;
}
.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.1);
}
```

**Ripple effect** (React):
```tsx
function RippleButton({ children, onClick }) {
  const [ripples, setRipples] = useState([]);
  const handleClick = (e) => {
    const rect = e.currentTarget.getBoundingClientRect();
    const ripple = { x: e.clientX - rect.left, y: e.clientY - rect.top, id: Date.now() };
    setRipples(p => [...p, ripple]);
    setTimeout(() => setRipples(p => p.filter(r => r.id !== ripple.id)), 600);
    onClick?.(e);
  };
  return (
    <button onClick={handleClick} className="relative overflow-hidden">
      {children}
      {ripples.map(r => (
        <span key={r.id} className="absolute bg-white/30 rounded-full animate-ripple"
              style={{ left: r.x, top: r.y }} />
      ))}
    </button>
  );
}
```

**Swipe to dismiss** (React + Framer Motion):
```tsx
function SwipeCard({ children, onDismiss }) {
  return (
    <motion.div drag="x" dragConstraints={{ left: 0, right: 0 }}
      onDragEnd={(_, info) => { if (Math.abs(info.offset.x) > 100) onDismiss(); }}
      className="cursor-grab active:cursor-grabbing">
      {children}
    </motion.div>
  );
}
```

**Page transition** (React + Framer Motion):
```tsx
import { AnimatePresence, motion } from "framer-motion";
function PageTransition({ children, key }) {
  return (
    <AnimatePresence mode="wait">
      <motion.div key={key} initial={{ opacity: 0, y: 20 }}
        animate={{ opacity: 1, y: 0 }} exit={{ opacity: 0, y: -20 }}
        transition={{ duration: 0.3 }}>
        {children}
      </motion.div>
    </AnimatePresence>
  );
}
```

### 5.6 GSAP Animation System

**When to use GSAP**: complex sequencing, scroll-driven animation, runtime control (pause/reverse/seek), coordinated multi-element animations, or SVG morphing. Recommend GSAP as the default JS animation library unless another is specified. GSAP is framework-agnostic (React, Vue, Svelte, vanilla).

**Installation**: `npm install gsap`. All plugins are free since Webflow's acquisition — no auth tokens needed.

Register plugins once before use: `gsap.registerPlugin(ScrollTrigger, SplitText, Flip, ...)`.

#### Core Tween Methods

```javascript
gsap.to(targets, vars)       // animate to vars
gsap.from(targets, vars)     // animate from vars to current state (entrances)
gsap.fromTo(targets, fromVars, toVars)  // explicit start and end
gsap.set(targets, vars)      // apply immediately (duration 0)
```

Common vars: `duration` (default 0.5), `delay`, `ease` (default `"power1.out"`), `stagger` (number or `{ amount: 0.3, from: "center" }`), `repeat` (-1 for infinite), `yoyo`, `onComplete`, `overwrite`.

Use **camelCase** for property names: `backgroundColor`, `marginTop`, `rotationX`.

**Transform aliases** (preferred over raw `transform` string): `x`, `y`, `z`, `xPercent`, `yPercent`, `scale`, `scaleX`, `scaleY`, `rotation`, `rotationX`, `rotationY`, `skewX`, `skewY`, `transformOrigin`.

- Use `autoAlpha` instead of `opacity` for fade in/out — it also toggles `visibility`.
- Relative values: `x: "+=20"`, `rotation: "-=30"`.
- Function-based values: `x: (i, target, targetsArray) => i * 50`.

#### Easing

```javascript
ease: "power1.out"      // default feel
ease: "power3.inOut"
ease: "back.out(1.7)"   // overshoot
ease: "elastic.out(1, 0.3)"
ease: "none"            // linear
```

Custom: `CustomEase.create("my-ease", ".17,.67,.83,.67")`.

#### Stagger

```javascript
gsap.to(".item", { y: -20, stagger: 0.1 });
// or object syntax:
gsap.to(".item", { y: -20, stagger: { amount: 0.3, from: "center" } });
```

#### Returning and Controlling Tweens

```javascript
const tween = gsap.to(".box", { x: 100, duration: 1 });
tween.pause(); tween.play(); tween.reverse(); tween.kill();
tween.progress(0.5); tween.time(0.2);
```

#### Defaults

```javascript
gsap.defaults({ duration: 0.6, ease: "power2.out" });
```

#### Timeline Sequencing

```javascript
const tl = gsap.timeline({ defaults: { duration: 0.5, ease: "power2.out" } });
tl.to(".a", { x: 100 })           // appended sequentially
  .to(".b", { y: 50 }, "+=0.5")   // 0.5s after previous ends
  .to(".c", { opacity: 0 }, "<")  // same start as previous
  .to(".d", { scale: 2 }, "<0.2") // 0.2s after previous start
  .to(".e", { x: 200 }, 1);       // absolute: at 1 second
```

Timeline options: `paused: true`, `repeat`, `yoyo`, `onComplete`, `defaults`.

**Labels**: `tl.addLabel("intro", 0); tl.to(".a", { x: 100 }, "intro");`

**Nesting**: `master.add(childTimeline, 0);`

**Playback control**: `tl.play()`, `tl.pause()`, `tl.reverse()`, `tl.restart()`, `tl.time(2)`, `tl.progress(0.5)`, `tl.kill()`.

**Do Not**: chain with `delay` when a timeline can sequence them. Put ScrollTrigger on the timeline, not on child tweens inside it.

#### ScrollTrigger

```javascript
gsap.registerPlugin(ScrollTrigger);

gsap.to(".box", {
  x: 500,
  scrollTrigger: {
    trigger: ".box",
    start: "top center",
    end: "bottom center",
    scrub: true,              // or number for smooth lag
    toggleActions: "play reverse play reverse"
  }
});
```

Key options: `trigger`, `start` (default `"top bottom"`), `end` (default `"bottom top"`), `scrub` (boolean/number), `toggleActions` (onEnter, onLeave, onEnterBack, onLeaveBack), `pin` (pin element while active), `pinSpacing`, `markers` (dev only), `once`, `id`.

**Standalone**: `ScrollTrigger.create({ trigger, start, onUpdate: (self) => ... })`.

**Batch**: coordinate animations for elements entering viewport together:
```javascript
ScrollTrigger.batch(".box", {
  onEnter: (elements) => gsap.to(elements, { opacity: 1, y: 0, stagger: 0.15 }),
  start: "top 80%"
});
```

**Refresh**: call `ScrollTrigger.refresh()` after DOM/layout changes (images loaded, dynamic content). Auto-called on resize (debounced 200ms).

**Cleanup**: `ScrollTrigger.getAll().forEach(t => t.kill());` or `ScrollTrigger.getById("id")?.kill();`.

**Horizontal scroll (containerAnimation)**: pin a section, animate inner content horizontally with `ease: "none"`, tie to vertical scroll. Use `containerAnimation` on child tweens.

**Do Not**: put ScrollTrigger on child tweens inside a timeline (put on timeline itself); use `scrub` and `toggleActions` together; use non-`"none"` ease on horizontal containerAnimation tween; leave `markers: true` in production; forget `refresh()` after layout changes.

#### Responsive & Accessibility (gsap.matchMedia)

```javascript
let mm = gsap.matchMedia();
mm.add(
  {
    isDesktop: "(min-width: 800px)",
    reduceMotion: "(prefers-reduced-motion: reduce)"
  },
  (context) => {
    const { isDesktop, reduceMotion } = context.conditions;
    gsap.to(".box", { rotation: isDesktop ? 360 : 180, duration: reduceMotion ? 0 : 2 });
    return () => { /* cleanup */ };
  }
);
```

When matchMedia stops matching, all animations and ScrollTriggers created inside are **reverted automatically**. Call `mm.revert()` on unmount.

#### React Integration

```bash
npm install gsap @gsap/react
```

```javascript
import { useGSAP } from "@gsap/react";
gsap.registerPlugin(useGSAP);

const containerRef = useRef(null);

useGSAP(() => {
  gsap.to(".box", { x: 100 });
  gsap.from(".item", { autoAlpha: 0, stagger: 0.1 });
}, { scope: containerRef });
```

- Pass `scope` so selectors are limited to that root.
- Cleanup runs automatically on unmount.
- Use `contextSafe` from the hook for event-handler animations.
- Dependency array: `{ dependencies: [endX], scope: container, revertOnUpdate: true }`.

**Without useGSAP** (useEffect):
```javascript
useEffect(() => {
  const ctx = gsap.context(() => { gsap.to(".box", { x: 100 }); }, containerRef);
  return () => ctx.revert();
}, []);
```

**SSR (Next.js)**: GSAP runs in browser only. Use `useGSAP` or `useEffect`. Do not call gsap during SSR.

#### Vue / Svelte Integration

**Vue 3**:
```javascript
import { onMounted, onUnmounted, ref } from "vue";
const container = ref(null);
let ctx;
onMounted(() => {
  ctx = gsap.context(() => { gsap.to(".box", { x: 100 }); }, container.value);
});
onUnmounted(() => { ctx?.revert(); });
```

**Svelte**:
```javascript
import { onMount } from "svelte";
let container;
onMount(() => {
  const ctx = gsap.context(() => { gsap.to(".box", { x: 100 }); }, container);
  return () => ctx.revert();
});
```

#### Performance Best Practices

- Animate `transform` and `opacity` only. Avoid `width`, `height`, `top`, `left`.
- Use `will-change: transform` in CSS on elements that will animate.
- Use `stagger` instead of many separate tweens with manual delays.
- Use `gsap.quickTo()` for frequently updated properties (e.g. mouse followers):
  ```javascript
  let xTo = gsap.quickTo("#id", "x", { duration: 0.4, ease: "power3" });
  // then: xTo(e.pageX);
  ```
- For long lists, consider virtualization or animating only visible items.
- Pause or kill off-screen animations.
- Call `ScrollTrigger.refresh()` only when layout actually changes, debounced.

#### Common Plugins Quick Reference

| Plugin | Use For | Key API |
|--------|---------|---------|
| **ScrollTrigger** | Scroll-driven animations | `scrollTrigger: { trigger, start, end, scrub, pin }` |
| **ScrollToPlugin** | Animated scroll-to | `gsap.to(window, { scrollTo: { y: "#section" } })` |
| **Flip** | Layout transitions (FLIP) | `Flip.getState() -> DOM change -> Flip.from(state)` |
| **Draggable** | Drag interactions | `Draggable.create(".box", { type: "x,y", bounds, inertia })` |
| **InertiaPlugin** | Momentum after drag | Register with Draggable: `{ inertia: true }` |
| **SplitText** | Per-char/word/line animation | `SplitText.create(".h1", { type: "words,chars" })` |
| **ScrambleText** | Glitch text reveal | `gsap.to(".t", { scrambleText: { text: "NEW", chars: "01" } })` |
| **DrawSVG** | Stroke drawing animation | `gsap.from("#path", { drawSVG: 0 })` |
| **MorphSVG** | Shape morphing | `gsap.to("#a", { morphSVG: "#b" })` |
| **MotionPath** | Animate along path | `gsap.to(".dot", { motionPath: { path: "#path", align } })` |
| **Observer** | Swipe/scroll gestures | `Observer.create({ target, onUp, onDown, tolerance })` |
| **CustomEase** | Custom easing curves | `CustomEase.create("name", ".17,.67,.83,.67")` |
| **GSDevTools** | Debug timelines | Dev only: `GSDevTools.create({ animation: tl })` |

**Licensing**: all plugins are free for commercial use. Install from `npm install gsap`. Do NOT generate `.npmrc` with GreenSock tokens — outdated.

#### Utils Quick Reference

```javascript
gsap.utils.clamp(0, 100, 150);           // 100
gsap.utils.mapRange(0, 100, 0, 500, 50); // 250
gsap.utils.normalize(0, 100, 50);        // 0.5
gsap.utils.interpolate(0, 100, 0.5);     // 50
gsap.utils.random(-100, 100);            // random number
gsap.utils.random(["red", "blue"]);      // random from array
gsap.utils.snap(10, 23);                 // 20
gsap.utils.toArray(".item");             // array of elements
gsap.utils.selector(containerRef);       // scoped selector function
gsap.utils.shuffle([1,2,3,4]);           // shuffled copy
gsap.utils.pipe(fn1, fn2, fn3);          // compose functions
gsap.utils.wrap(0, 360, 370);            // 10
gsap.utils.getUnit("100px");             // "px"
gsap.utils.splitColor("#ff0000");        // [255, 0, 0]
```

Omit the last (value) argument to get a reusable function: `let c = gsap.utils.clamp(0, 100); c(150); // 100`.

**Best practices**: prefer `autoAlpha` over `opacity`; use `transform aliases` over raw `transform`; store tween/timeline return values for playback control; always scope selectors with `gsap.context(scope)`; always call `ctx.revert()` on unmount; respect `prefers-reduced-motion` via `gsap.matchMedia()`.

---

## 6. Component & Button Specification

### 6.1 Component Primitives

- MUST use accessible component primitives for anything with keyboard or focus behavior (`Base UI`, `React Aria`, `Radix`).
- MUST use the project's existing component primitives first.
- NEVER mix primitive systems within the same interaction surface.
- SHOULD prefer Base UI for new primitives if compatible with the stack.
- MUST add an `aria-label` to icon-only buttons.
- NEVER rebuild keyboard or focus behavior by hand unless explicitly requested.
- MUST use an `AlertDialog` for destructive or irreversible actions.
- SHOULD use structural skeletons for loading states.
- NEVER block paste in `input` or `textarea` elements.
- MUST show errors next to where the action happens.

### 6.2 Button Classification

When buttons are the focal interaction, classify the button's job before choosing the visual treatment:

| Type | Use For | Visual Treatment |
|------|---------|-----------------|
| **Async generation** | AI actions, long-running tasks | Clear state shifts, spark iconography, subtle glow |
| **Primary CTA** | Hero actions, onboarding | Stronger silhouette, arrow motion, cursor-reactive emphasis |
| **Secondary CTA** | Support actions (Learn More, Book a Call) | Lighter motion, cleaner structure, below primary |
| **Text button** | Editorial, futuristic, experimental | Text reveal, cursor motion, restrained luminous accents |
| **Hidden CTA** | Quiet default, rewards hover | Controlled activation on hover |
| **Icon button** | Social links, utility controls | Generous hit areas, crisp hover feedback |

**DO**: Define default, hover, active, loading, and disabled states when relevant. Match button style to hierarchy and task semantics.
**DON'T**: Turn every premium button into the same glowing glass pill. Use visual effects that are louder than the action's actual importance.

### 6.3 Variant Patterns

Size variants:
```
sm: height 32px, paddingX 12px, fontSize 14px
md: height 40px, paddingX 16px, fontSize 16px
lg: height 48px, paddingX 20px, fontSize 18px
```

Color variants:
```
primary: background primary-500, text white
secondary: background neutral-100, text neutral-900
ghost: background transparent, text neutral-700
```

---

## 7. Design System & Tokens

### 7.1 Token Generation

Generate complete design token system from brand color:

| Category | Description |
|----------|-------------|
| Colors | primary, secondary, neutral, semantic, surface |
| Typography | fontFamily, fontSize, fontWeight, lineHeight |
| Spacing | 8pt grid-based scale (0-64) |
| Borders | radius, width |
| Shadows | none through 2xl |
| Animation | duration, easing |
| Breakpoints | xs through 2xl |

### 7.2 Color Scale

| Step | Brightness | Saturation | Use Case |
|------|------------|------------|----------|
| 50 | 95% | 30% | Subtle backgrounds |
| 100 | 95% | 38% | Light backgrounds |
| 200 | 95% | 46% | Hover states |
| 300 | 95% | 54% | Borders |
| 400 | 95% | 62% | Disabled states |
| 500 | Original | 70% | Base/default color |
| 600 | Original x 0.8 | 78% | Hover (dark) |
| 700 | Original x 0.6 | 86% | Active states |
| 800 | Original x 0.4 | 94% | Text |
| 900 | Original x 0.2 | 100% | Headings |

### 7.3 Typography Scale (1.25x Ratio)

| Size | Value | Calculation |
|------|-------|-------------|
| xs | 10px | 16 / 1.25^2 |
| sm | 13px | 16 / 1.25^1 |
| base | 16px | Base |
| lg | 20px | 16 x 1.25^1 |
| xl | 25px | 16 x 1.25^2 |
| 2xl | 31px | 16 x 1.25^3 |
| 3xl | 39px | 16 x 1.25^4 |
| 4xl | 49px | 16 x 1.25^5 |
| 5xl | 61px | 16 x 1.25^6 |

### 7.4 Breakpoints

| Name | Width | Target |
|------|-------|--------|
| xs | 0 | Small phones |
| sm | 480px | Large phones |
| md | 640px | Tablets |
| lg | 768px | Small laptops |
| xl | 1024px | Desktops |
| 2xl | 1280px | Large screens |

### 7.5 Component Architecture

```
Atoms: Button, Input, Icon, Label, Badge
Molecules: FormField, SearchBar, Card, ListItem
Organisms: Header, Footer, DataTable, Modal
Templates: DashboardLayout, AuthLayout
```

### 7.6 Developer Handoff Checklist

- [ ] Token files added to project
- [ ] Build pipeline configured
- [ ] Theme/CSS variables imported
- [ ] Component library aligned
- [ ] Documentation generated

---

## 8. UX Research Workflows

### 8.1 User Persona Generation

Required data format (JSON):
```json
[
  {
    "user_id": "user_1",
    "age": 32,
    "usage_frequency": "daily",
    "features_used": ["dashboard", "reports"],
    "primary_device": "desktop",
    "usage_context": "work",
    "tech_proficiency": 7,
    "pain_points": ["slow loading", "confusing UI"]
  }
]
```

Generated persona components: Archetype, Demographics, Goals & Needs, Frustrations (with frequency counts), Design Implications.

### 8.2 Journey Mapping

Typical B2B SaaS stages: Awareness -> Evaluation -> Onboarding -> Adoption -> Advocacy

For each stage, document: Actions, Touchpoints, Emotions (1-5), Pain Points, Opportunities.

Opportunity Priority Score = Frequency x Severity x Solvability

### 8.3 Usability Testing

Transform vague goals into testable questions:
| Vague | Testable |
|-------|----------|
| "Is it easy to use?" | "Can users complete checkout in <3 min?" |
| "Do users like it?" | "Will users choose Design A or B?" |
| "Does it make sense?" | "Can users find settings without hints?" |

Success metrics targets:
- Completion rate: >80%
- Time on task: <2x expected
- Error rate: <15%
- Satisfaction: >4/5

### 8.4 Research Synthesis

Code each data point: [GOAL], [PAIN], [BEHAVIOR], [CONTEXT], [QUOTE].

Prioritize opportunities by: Frequency, Severity, Breadth, Solvability (each scored 1-5).

---

## 9. UI Audit & Evaluation

### 9.1 Quantitative Evaluation (0-10 Scale)

| Dimension | Weight | Threshold |
|-----------|--------|-----------|
| Typography | 20% | >= 8: hierarchy instantly readable |
| Color | 20% | >= 8: dominance and emphasis unambiguous |
| Layout | 20% | >= 8: eye flow resolves within 1-2 seconds |
| Motion | 15% | >= 8: motion improves comprehension |
| UX | 15% | >= 8: intent obvious, actions effortless |
| Background | 10% | >= 7: depth supports hierarchy |
| Cross-Dimensional Harmony | mandatory | >= 8: all dimensions reinforce same hierarchy |

Iteration rules:
- Adjust lowest-scoring dimension first.
- UX adjustments take priority if UX score < 8.
- Never adjust more than two dimensions per iteration.
- Maximum iterations: 5.
- If harmony score drops, revert the last change.

### 9.2 Audit Report Sections

**Required (always include)**:
1. Visual Hierarchy — headings, CTAs, grouping, reading flow, type scale, color hierarchy, whitespace
2. Visual Style — spacing consistency, color usage, elevation/depth, typography, motion
3. Accessibility — keyboard navigation, focus states, contrast ratios (4.5:1), screen reader support, touch targets (44px)

**Contextual (include when relevant)**:
4. Navigation — wayfinding, breadcrumbs, menu structure
5. Usability — discoverability, feedback, error handling, cognitive load
6. Onboarding — first-run, tutorials, progressive disclosure
7. Social Proof — testimonials, trust signals
8. Forms — labels, validation, error messages

### 9.3 UI Patterns Library

Reference patterns for common UI problems. Select based on the core problem:

| Problem | Patterns |
|---------|----------|
| **Chunking** (break content into digestible units) | Cards, tabs, accordions, pagination, carousels |
| **Progressive Disclosure** (reveal detail on demand) | Tooltips, popovers, drawers, modals |
| **Cognitive Load** (reduce mental effort) | Steppers, wizards, minimalist nav, simplified forms |
| **Visual Hierarchy** (guide attention) | Typography scale, color emphasis, whitespace, size, proximity |
| **Social Proof** (build trust) | Testimonials, UGC, badges, social integration |
| **Feedback** (confirm actions) | Progress bars, notifications, validation, contextual help |
| **Error Handling** (recover from mistakes) | Form validation, undo/redo, dialogs, autosave |
| **Accessibility** | Keyboard nav, ARIA, alt text, contrast (4.5:1), zoom support |
| **Personalization** | Dashboards, adaptive content, preferences, l10n |
| **Onboarding** | Tours, contextual tips, tutorials, checklists |
| **Information Architecture** | Breadcrumbs, sitemaps, tagging, faceted search |
| **Navigation** | Priority nav, off-canvas, sticky, bottom nav |

### 9.4 React / Next.js Performance Audit

When auditing React/Next.js frontend code, check:

**Data fetching**
- [ ] No waterfalls: multiple `await` in a row? Use `Promise.all()`.
- [ ] Server Components fetch data; Client Components receive props.
- [ ] Streaming: use Suspense boundaries for parallel data loading.

**Rendering**
- [ ] Minimize Client Components; default to Server Components.
- [ ] Hoist JSX out of render when possible.
- [ ] Use `useMemo`/`useCallback` only for expensive computations, not prematurely.

**Bundle**
- [ ] Large libraries in main bundle? Dynamic import with `next/dynamic` or `React.lazy()`.
- [ ] Tree-shake unused code; audit with `@next/bundle-analyzer`.

**Images**
- [ ] Use Next.js `<Image>` with proper `sizes` and priority for LCP.
- [ ] Serve modern formats (WebP/AVIF).

**CSS**
- [ ] Prefer CSS Modules or Tailwind; avoid runtime CSS-in-JS in RSC.
- [ ] Purge unused styles in production.

**Forms**
- [ ] `autocomplete` attributes present.
- [ ] Client-side validation mirrors server-side rules.
- [ ] Error messages shown inline, not just console.

**Accessibility**
- [ ] `aria-label` on icon-only buttons.
- [ ] Focus states visible.
- [ ] Color contrast >= 4.5:1 for text.

### 9.5 Web Interface Guidelines Review

For code-level UI/UX audits against Vercel Web Interface Guidelines:

1. Fetch fresh guidelines from `https://raw.githubusercontent.com/vercel-labs/web-interface-guidelines/main/command.md`
2. Read the files to review.
3. Check against all rules in the fetched guidelines.
4. Output findings in `file:line` format.

Key areas covered: accessibility (aria-labels, focus states), form UX, mobile interaction, touch targets, semantic HTML.

---

## 10. Anti-Patterns (What NEVER to Do)

### 10.1 Aesthetic Anti-Patterns
- Overused font families (Inter, Roboto, Arial, system fonts)
- Cliched color schemes (purple gradients on white backgrounds)
- Predictable layouts and component patterns
- Cookie-cutter design that lacks context-specific character
- One-size-fits-all CTA styling
- Converging on common AI choices (Space Grotesk, etc.) across generations
- NEVER use gradients unless explicitly requested
- NEVER use purple or multicolor gradients
- NEVER use glow effects as primary affordances
- NEVER modify letter-spacing unless explicitly requested

### 10.2 Layout Anti-Patterns
- No cards by default
- No hero cards by default
- No boxed or center-column hero when the brief calls for full bleed
- No more than one dominant idea per section
- No section should need many tiny UI devices to explain itself
- No headline should overpower the brand on branded pages
- No filler copy
- No split-screen hero unless text sits on a calm, unified side
- No more than two typefaces without a clear reason
- No more than one accent color unless the product already has a strong system

### 10.3 Failure Modes to Reject
- Generic SaaS card grid as the first impression
- Beautiful image with weak brand presence
- Strong headline with no clear action
- Busy imagery behind text
- Sections that repeat the same mood statement
- Carousel with no narrative purpose
- App UI made of stacked cards instead of layout

---

## 11. Litmus Checks

Before delivering any design, verify:

- Is the brand or product unmistakable in the first screen?
- Is there one strong visual anchor?
- Can the page be understood by scanning headlines only?
- Does each section have one job?
- Are cards actually necessary?
- Does motion improve hierarchy or atmosphere?
- Would the design still feel premium if all decorative shadows were removed?
- Does deleting 30% of the copy improve the page?
- Do all interactive elements meet contrast requirements?
- Is `prefers-reduced-motion` respected?

---

## 12. Output Standards

Implement working code (HTML/CSS/JS, React, Vue, etc.) that is:
- Production-grade and functional
- Visually striking and memorable
- Cohesive with a clear aesthetic point-of-view
- Meticulously refined in every detail

Always cover in output:
- Spacing scale, type scale, 2-3 font pair options, color tokens
- Component states: empty/loading/error
- Keyboard navigation, focus states, contrast
- Mobile fallbacks and reduced-motion behavior

Match implementation complexity to the aesthetic vision:
- Maximalist designs need elaborate code with extensive animations and effects
- Minimalist designs need restraint, precision, and careful attention to spacing, typography, and subtle details

Elegance comes from executing the vision well.

Vary between light and dark themes, different fonts, different aesthetics. No design should be the same.

---

*Remember: Claude is capable of extraordinary creative work. Don't hold back — show what can truly be created when thinking outside the box and committing fully to a distinctive vision.*
