# Landing Page Styling Guide

This document captures the design system and Tailwind CSS patterns used to create the modern, dark-themed VoxLib landing page. You can use these utility classes to replicate this exact look and feel in other Next.js or Tailwind-based projects.

## Core Palette & Background

The page relies heavily on the `zinc` color scale for achieving a premium, muted dark mode look, avoiding harsh deep blacks or blues.

- **Main Background Add-on:** A subtle gradient.
  - classes: `min-h-screen bg-gradient-to-br from-zinc-950 via-zinc-900 to-zinc-950 text-white`
- **Text Defaults:** White for primary headers, `text-zinc-400` for subtitles and body.

## Headlines & Typography

The main hero title uses tight tracking and a smooth horizontal text gradient to create a "shimmering metallic" feeling.

- **Hero Title Classes:** `text-5xl md:text-7xl font-bold tracking-tight bg-gradient-to-r from-white via-zinc-300 to-zinc-500 bg-clip-text text-transparent`
- **Sub-headline Classes:** `text-lg md:text-xl text-zinc-400 leading-relaxed`

## The "Live" Badge / Indicator Pill

For tagging the top of the hero section (e.g., "AI-Powered", "Live", or "Beta"), the page uses a pill-shaped badge with a glowing green dot next to the text.

- **Wrapper:** `inline-flex items-center gap-2 rounded-full border border-zinc-700/50 bg-zinc-800/50 px-4 py-1.5 text-sm text-zinc-400`
- **Pulsing Dot Component:**

  ```jsx
  <span className="relative flex h-2 w-2">
    <span className="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
    <span className="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
  </span>
  ```

## Action Buttons (CTAs)

The design avoids loud colors for buttons, opting instead for a high-contrast inverted primary button and a ghost secondary button.

- **Primary Button (Get Started):**
  - classes: `inline-flex items-center justify-center rounded-lg bg-white text-zinc-900 px-8 py-3 text-base font-semibold hover:bg-zinc-200 transition-colors`
- **Secondary Button (Learn More):**
  - classes: `inline-flex items-center justify-center rounded-lg border border-zinc-700 text-zinc-300 px-8 py-3 text-base font-semibold hover:bg-zinc-800 transition-colors`

## Feature Pills

Instead of traditional bullet points, features are listed below the CTA as small, transparent pills.

- **Pill Classes:** `rounded-full bg-zinc-800/60 border border-zinc-700/40 px-3 py-1 text-sm text-zinc-400`

## Separators & Borders

For dividing sections (like the footer), a slightly transparent line is used to avoid jarring contrasts.

- **Footer/Divider:** `border-t border-zinc-800/50` text uses `text-sm text-zinc-600`

## Implementation Checklist

To use this style elsewhere:

1. Ensure your Tailwind config has default colors enabled (especially Zinc and Emerald).
2. Set your root/body background to pure black or `bg-zinc-950`.
3. Leverage `/50` or `/60` opacity modifiers in Tailwind on your background blocks and borders to get the glass/translucent dark mode style (e.g. `bg-zinc-800/50`).
4. Apply linear text gradients for massive H1 headers using `bg-clip-text text-transparent`.
