# F-Statistic Interactive Guide

A modern, interactive 2026-style explainer that teaches the **F-statistic** — the ratio that decides whether differences between groups are real signal or just random noise. Built as a two-page HTML experience with zero build step: open either file in a browser and everything works.

---

## Contents

| File | Purpose |
|------|---------|
| `f-statistic-explained.html` | Main educational guide with a sticky left sidebar and 11 structured sections. |
| `f-statistic-visualizations.html` | Companion interactive lab with live charts, Monte Carlo simulations, and an ANOVA simulator. |
| `README.md` | This file. |

---

## Quick Start

1. Open `f-statistic-explained.html` in any modern browser (Chrome, Safari, Firefox, Edge).
2. Use the left sidebar to jump between sections.
3. Click **"Open Visualization Lab"** in the hero, the sidebar, or the closing card to launch the interactive companion.
4. From the Visualization Lab, use **"Back to Main Guide"** in the sidebar to return.

No server, no install, no dependencies to set up — everything loads via CDN.

---

## Main Guide (`f-statistic-explained.html`)

A text-and-diagram-first walkthrough designed to build intuition before introducing math.

**Sections:**
1. **Introduction** — what the F-statistic is and why it matters
2. **Signal vs. Noise** — the core analogy behind every F calculation
3. **The Formula** — from plain English to MSB/MSW to the full mathematical form
4. **Visual Intuition** — side-by-side SVG illustrations for F < 1 and F > 1
5. **MSB & MSW Explained** — what the numerator and denominator actually measure
6. **Worked Example** — step-by-step calculation with three teaching methods (F = 48)
7. **Interpreting F Values** — what F ≤ 1, 1 < F < critical, and F ≫ critical mean
8. **P-value & Decision** — connecting F to the F-distribution and significance testing
9. **Interactive Playground** — slider-driven signal/noise demo
10. **Real-World Applications** — six domains where F-tests are used
11. **Summary** — one-line memory hook and key takeaways

**Highlights:** MathJax equations, scroll-spy sidebar, gradient hero, responsive grid layouts, and tag-based color coding (signal / noise / good / bad).

---

## Visualization Lab (`f-statistic-visualizations.html`)

A companion page that turns every concept from the guide into something you can touch and drag.

**Sections:**
1. **Live ANOVA Simulator** — adjust three group means, within-group standard deviation, and sample size; F-statistic, p-value, and decision update in real time
2. **Scatter Visualization** — each sampled observation is plotted so you can see clusters form
3. **F-Distribution Curve** — draws the true F-distribution for your df₁/df₂, shades the α=0.05 rejection region, and marks your observed F
4. **Signal vs Noise Side-by-Side** — contrasts a low-F and high-F scenario in miniature charts
5. **Random Sampling Under H₀** — runs 1,000 simulations where groups are truly identical and plots the resulting F histogram; confirms the 5% tail empirically
6. **Critical F Values Reference** — classic α = 0.05 lookup table

**Under the hood:** real statistical computations in plain JavaScript, including a Box-Muller Gaussian sampler, regularized incomplete beta function for the F-distribution CDF, custom F PDF implementation, and bisection-based critical value solver. Charts rendered with Chart.js (loaded from CDN).

---

## Design System

Both pages share a consistent modern dark aesthetic:

- **Color palette:** deep navy backgrounds with purple (`#7b5cff`), teal (`#00e0c7`), pink (`#ff6b9d`), and amber (`#ffb648`) accents
- **Typography:** Inter sans-serif with gradient-clipped headings
- **Surfaces:** glassmorphic cards, subtle grid overlays, soft glows
- **Navigation:** sticky left sidebar with section icons and scroll-spy active indicators
- **Responsive:** single-column mobile layout below 900px

---

## Technical Details

- Pure HTML + CSS + vanilla JS — no bundler, no framework.
- External dependencies (CDN only): MathJax (main guide), Chart.js (visualization lab).
- Accessibility: semantic landmarks, high contrast, keyboard-navigable links.
- Browser support: any modern evergreen browser (ES6+ required).

---

## Learning Path

For best results, read in this order:

1. Start with the **Main Guide**, section by section, top to bottom.
2. When you reach the **Playground** (section 9), spend a minute dragging sliders.
3. Click through to the **Visualization Lab** and run the **1,000-sample Monte Carlo** — this is the "aha" moment for seeing why α = 0.05 is what it is.
4. Return to the **Summary** and re-read the one-line hook. It should now feel obvious.

---

## One-Line Summary

> F measures *how loud the signal is relative to the noise*, and the p-value tells you *whether that loudness is surprising enough to trust*.
