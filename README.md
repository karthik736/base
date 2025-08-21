# Interactive-Educational-Module-
"An interactive educational module designed to make learning engaging and accessible. Includes dynamic lessons, quizzes, and visual aids to support self-paced learning and knowledge retention."
# Optics — Interactive Educational Module (Class 10)

**Goal:** Explain the thin-lens model with an interactive, visual simulator that helps Class 10 students build intuition quickly while aligning with textbook conventions.

## Design & Approach (Brief)
- **Immediate feedback:** Sliders recompute the ray diagram in real time so learners see cause → effect (u, f, h₀ → image position/size, case label).
- **Familiar language:** Badge shows “Real & Inverted / Virtual & Erect / Image at Infinity”; a short explanation block translates outputs to exam terms.
- **Guided exploration:** Presets cover canonical positions (u>2f, u=2f, f<u<2f, u=f, u<f; concave any u). Optional 5-Q quiz for quick recall.
- **Clean layout:** Theory cards (Thin Lens, Magnification, Principal Rays) above; two-column grid with controls left, diagram right.

## Technical Decisions
- **React + Vite** for fast dev + small bundles.
- **SVG** for crisp, labeled ray geometry (easier than canvas for lines/markers/text).
- **Tailwind via CDN** to avoid a build pipeline; keeps repo light and portable.
- **GitHub Pages** hosting. Vite configured with `base: "/base/"` and `.nojekyll` to ensure assets load correctly.

## Physics Model
- **Thin lens:** \\(\\tfrac{1}{f} = \\tfrac{1}{v} - \\tfrac{1}{u}\\) ⇒ \\(v = 1/(1/f + 1/u)\\).
- **Cartesian signs:** lens at origin; left negative, right positive. Convex: \\(f>0\\), Concave: \\(f<0\\); object on the left ⇒ \\(u<0\\).
- **Magnification:** \\(m=v/u\\), \\(h_i = m h_0\\). Virtual image is dashed; real is solid.

## Structure
Derived values are O(1); SVG re-renders are cheap. If we add heavier visuals later, split components and memoize.

## Accessibility & UX
- Single `<h1>` per route; high contrast ray colors; large slider hit-targets.
- Future: ARIA for sliders and keyboard shortcuts.

## Future Enhancements
- Add Waves/Fluids pages under the same sidebar, mirror sign-conventions for mirrors, export diagram as PNG, richer quizzes, and mobile fine-tuning.
