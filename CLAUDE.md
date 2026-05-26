Project: STEM Math Learning Ecosystem
Paste this into Claude Code or a new chat to continue

What was built — 3 standalone HTML files:
quick_math_trainer.html (index.html) — Mental math drill app

8 modes: Addition, Subtraction, Multiplication, Division, Squares/Roots, Powers of 2, Fractions, Estimation, Mixed
Phone-style numpad (1-2-3 top row), no keyboard popup
Easy/Medium/Hard difficulty, 10/20/30 questions per session
Per-question tips shown after 3s, streak tracker, results screen
3-tab Master Guide: 7-day plan, shortcut tricks, Chinese methods (Suanpan, Vedic, An Suan, Gugudan, Flash Anzan)

math_roadmap.html — Visual topic reference

Beginner → Expert across Physics, Engineering, CS, AI
Filterable by field, expandable topic cards with subtopics

math_knowledge_tree.html — Interactive learning tree

18 nodes across 7 chapters, prerequisite-locked
Each node: 4 concept blocks, formulas, mental shortcut, 3-question quiz (67% to pass)
XP system, progress bar, localStorage persistence
Filter by STEM / CS / AI

mental_math_essentials.html — Static reference page
  Expandable cards grouped by category (addition, multiplication, division, estimation, fractions, powers)
  Filter bar by category + live search
  Inline multiplication table 1–12

All files live in the repo root (no subdirectories).

---

Design System (use this for all new pages)

Fonts: Outfit (body) + DM Mono (labels, code, badges) via Google Fonts
  @import url('https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,400;0,500;1,400&family=Outfit:wght@300;400;600;700;800&display=swap');

CSS variables:
  --bg: #f5f0e8        (warm parchment background)
  --ink: #1a1208       (near-black text)
  --mid: #6b5e45       (muted brown for secondary text)
  --faint: #e2d9c8     (light border / divider color)
  --card: #fff9f0      (card background)
  --gold: #d4860a      (primary accent — links, highlights)
  --green: #2d7a4f     (success / positive)
  --red: #c0392b       (error / negative)
  --blue: #1a5f9e      (info)
  --purple: #6b3fa0    (extra accent)
  --shadow: 0 2px 0 #1a120820

Background texture: subtle grid SVG pattern via background-image + radial gradient overlay

Layout: single-column, max-width 680px (trainer) or 900px (reference pages), centered, padding 24px

Header pattern:
  .app-header — flex row, space-between, logo left (DM Mono 11px uppercase letter-spacing:3px) + back link right
  Back link: pill shape, border --faint, hover → --gold

Cards:
  background: --card, border: 1.5px solid --faint, border-radius: 16px, box-shadow: --shadow
  Hover: border-color → --gold, translateY(-2px)
  Color themes: theme-gold / theme-green / theme-blue / theme-red / theme-purple
    Each theme sets .card-icon background and .card-tag background + text color

Typography:
  Screen titles: font-weight 800, letter-spacing -1px, clamp(2rem, 5vw, 3.2rem)
  Section labels: DM Mono 11px, letter-spacing 3px, uppercase, color --mid
  Card tags: DM Mono 10px, letter-spacing 1px, uppercase, pill shape

Filter bar: pill buttons (DM Mono 12px), active state = --ink background + --bg text

Code/formula blocks:
  .formula — dark (--ink bg, --bg text), centered, DM Mono
  .example — light (--faint bg), DM Mono, .label sub-header in --mid

Step lists: numbered circle badges (--ink bg, --bg text, 24px), step text with <em> in --gold

Tables (.ref-table): first column DM Mono --gold, header DM Mono 10px uppercase --mid, row dividers --faint

---

Suggested next tasks:

Spaced repetition for wrong answers in the trainer
Worked examples with step-by-step solutions in the knowledge tree
More advanced nodes (Real Analysis, Stochastic Calculus)
Daily streak calendar / heatmap
Formula reference search app
