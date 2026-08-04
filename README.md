# Chroma Target Engine

A target-shooting mini-game built entirely with declarative HTML markups and custom layout styling rules. It bypasses traditional DOM manipulation by running its core loop, collision detection, and score management directly through browser-level layout recalculations.

## Overview & Value Proposition

Most browser games rely on `requestAnimationFrame` and event listeners to manage state, evaluate collisions, and increment scores. This repository demonstrates an alternative strategy: offloading the entire game state machine to native document traversal engine capabilities.

By using hidden forms, standard selectors, keyframe paths, and counter properties, this engine demonstrates how far standard styling markup can be pushed to handle state management without external script execution.

## How It Works

* **State Tracking:** Hidden `<input type="checkbox">` elements serve as boolean state containers.
* **Collision Engine:** Standard `<label>` nodes styled as floating targets bind directly to hidden inputs via `for` attributes, triggering click states.
* **Score Calculation:** CSS `counter-reset` on the parent container tracks checked inputs via `:checked` pseudo-classes, updating dynamic content pseudo-elements (`::after`) instantly.
* **Target Lifetime:** CSS Keyframe trajectories control movement paths across the vector space, while a timed keyframe screen reveals a end-game screen after 25 seconds.

## Key Features

* Zero runtime overhead outside standard DOM/CSS parsing pipelines.
* Smooth 60fps animations offloaded directly to GPU layer trajectories.
* State-driven scoring system powered by `:checked` pseudo-selectors and `counter-increment` rules.
* Self-contained restart mechanism via embedded page triggers.

## Tech Stack Breakdown

* **Markup:** Semantic HTML5 (`<input>`, `<label>`, `<header>`)
* **Styling Engine:** Keyframes, CSS Counters, Pseudo-Classes, CSS Transforms

## Prerequisites & Web-Based Quick Start

No local Node.js environment, web server, or build tooling required. You can open and inspect this directly in your browser.

### Option 1: Run via GitHub Codespaces

1. Press `.` (dot) on this repository page or click **Code > Open with Codespaces**.
2. Once the workspace loads, launch the `Live Preview` extension or open `index.html` directly in the built-in browser window.

### Option 2: Local Browser Quick Start

1. Download or download the source directly.
2. Open `index.html` using any standard browser.

## Repository Structure

```text
chroma-target-engine/
├── .github/
│   └── workflows/
│       └── validation.yml  # Automated HTML/CSS markup validator pipeline
├── .gitignore             # Excludes system clutter and editor overrides
├── index.html             # Document structure, inputs, and semantic nodes[cite: 1]
├── style.css              # Animation rules, state engine, and layout logic
└── LICENSE                # Open-source MIT usage guidelines
```

## Roadmap

[ ] Add multi-tier target scoring using varying hit-box scales.

[ ] Build custom difficulty settings via alternative CSS selector layers.

[ ] Experiment with pure CSS streak counters and multiplier states.
