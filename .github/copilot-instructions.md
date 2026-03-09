---
name: workspace-instructions
description: Always-on instructions for the Generative AI for Developers project. Covers project overview, development workflow, screenshot-replication conventions, and best practices for AI-assisted development.
---

# Generative AI for Developers - Workspace Instructions

## Project Overview

This workspace contains a static DocuSign-style marketing homepage focused on intelligent agreement management and generative AI messaging. The site is built with HTML and Tailwind CSS, and optimized for fast visual iteration from screenshot references.

Key technologies:

- **Frontend**: HTML5, Tailwind CSS 3.4
- **Build Tools**: npm, Tailwind CLI
- **No Backend**: Static site hosted via file system or simple server

## Development Workflow

- **Setup**: Run `npm install` to install dependencies (Tailwind CSS).
- **Build CSS**: Use `npm run build-css` to compile Tailwind styles from `input.css` to `output.css`. This command watches for changes.
- **View Site**: Open `index.html` in a web browser. Ensure `output.css` is up-to-date.
- **No Testing**: Manual testing only; verify layout and responsiveness in different browsers.
- **Deployment**: Static files can be served from any web server or hosting platform.

## Screenshot Replication Playbook

When implementing from a screenshot, prioritize structure and hierarchy over exact pixel cloning.

- Match in this order: **section order -> spacing rhythm -> typography scale -> color mood -> component details**.
- Recreate long-form marketing pages as stacked blocks with clear transitions (hero, trust bar, feature grid, social proof, CTA, dense footer).
- If source assets are unavailable (logos, product screenshots, photos), use clean placeholders with matching shape, contrast, and composition.
- Keep copy concise and product-oriented; use DocuSign/IAM language patterns from the existing page.
- Preserve responsiveness while matching desktop intent; mobile should stack naturally without changing section meaning.

## Current Page Blueprint

The homepage in `index.html` follows this order and future updates should preserve it unless explicitly requested:

1. Sticky top navigation with utility CTA buttons
2. High-contrast purple gradient hero with headline and two CTAs
3. Partner/logo strip
4. AI-powered agreement management intro + 2x2 capability cards
5. IAM highlight split section
6. Workflow/integration banner section on purple background
7. Trust and recognition cards + logo chips
8. Company outcomes/stat cards
9. Recommended content row
10. Large pre-footer CTA banner
11. Multi-column enterprise footer + legal bar

## Styling Conventions

All colors must adhere to the custom theme defined below. Use Tailwind CSS classes exclusively (e.g., `bg-blue-500`, `text-parchment-700`). Avoid arbitrary values unless absolutely necessary—reference this palette for consistency.

Typography and layout conventions:

- Use `Sora` for major headings and `Manrope` for body/UI text.
- Use rounded cards (`rounded-2xl` to `rounded-3xl`), soft borders (`border-black-100`), and layered gradients for hero and feature emphasis.
- Prefer `max-w-[1200px]` containers with `px-4 md:px-6` for desktop alignment.
- Keep interactions subtle: `hover:bg-*`, `hover:text-*`, and lightweight transitions.

### Color Palette

Keep all colors within this theme. Use Tailwind CSS classes.

--color-blue-50: #ede5ff;
--color-blue-100: #dbccff;
--color-blue-200: #b899ff;
--color-blue-300: #9466ff;
--color-blue-400: #7033ff;
--color-blue-500: #4d00ff;
--color-blue-600: #3d00cc;
--color-blue-700: #2e0099;
--color-blue-800: #1f0066;
--color-blue-900: #0f0033;
--color-blue-950: #0b0024;

--color-parchment-50: #f7f1ed;
--color-parchment-100: #f0e3db;
--color-parchment-200: #e0c7b8;
--color-parchment-300: #d1ab94;
--color-parchment-400: #c28f70;
--color-parchment-500: #b3744d;
--color-parchment-600: #8f5c3d;
--color-parchment-700: #6b452e;
--color-parchment-800: #472e1f;
--color-parchment-900: #24170f;
--color-parchment-950: #19100b;

--color-vibrant-coral-50: #ffe6e6;
--color-vibrant-coral-100: #fecdcd;
--color-vibrant-coral-200: #fd9b9b;
--color-vibrant-coral-300: #fd6868;
--color-vibrant-coral-400: #fc3636;
--color-vibrant-coral-500: #fb0404;
--color-vibrant-coral-600: #c90303;
--color-vibrant-coral-700: #970202;
--color-vibrant-coral-800: #640202;
--color-vibrant-coral-900: #320101;
--color-vibrant-coral-950: #230101;

--color-black-50: #f3f1f1;
--color-black-100: #e8e3e3;
--color-black-200: #d1c7c7;
--color-black-300: #b9acac;
--color-black-400: #a29090;
--color-black-500: #8b7474;
--color-black-600: #6f5d5d;
--color-black-700: #534646;
--color-black-800: #382e2e;
--color-black-900: #1c1717;
--color-black-950: #131010;

### Usage Guidelines

- **Primary Colors**: Blue for CTAs, links, and headers.
- **Backgrounds**: Parchment for subtle, warm backgrounds; white for content areas.
- **Accents**: Vibrant coral for highlights or secondary actions.
- **Text**: Black shades for readability; avoid low-contrast combinations on gradients.
- **Responsive Design**: Use Tailwind's responsive prefixes (sm:, md:, lg:) for mobile-first layouts.
- **Semantic HTML**: Structure pages with proper sections, headers, and navigation.

## Architecture Decisions

- **Static Site**: No JavaScript or frameworks to keep it lightweight and focused on content.
- **Custom Tailwind Config**: Extended with project-specific colors via `tailwind.config.js`.
- **Flat File Structure**: Core files are in root for simplicity.
- **No Dynamic Features**: Suitable for a demo; expand with JS if interactivity is required.
- **Visual-First Composition**: Sections are authored directly in `index.html` for rapid design iteration.

## Potential Pitfalls

- **CSS Build Required**: Always run the build command before viewing changes; `output.css` is generated from `input.css` and class scanning.
- **Browser Compatibility**: Test in modern browsers; no fallbacks for older versions.
- **Static Limitations**: Can't handle forms, APIs, or user data—consider adding a backend for production use.
- **Placeholder Asset Drift**: During screenshot recreation, placeholders can become inconsistent; keep card ratios and spacing uniform.
- **Tailwind Content Globs**: Keep `content` patterns narrow to avoid scanning `node_modules`.

## Key Files

- `index.html`: Main long-form homepage with all marketing sections.
- `tailwind.config.js`: Custom color configuration.
- `input.css`: Tailwind directives and CSS variables.
- `output.css`: Compiled styles (generated).
- `package.json`: Dependencies and build scripts.

## Visual QA Checklist

Before finalizing UI edits:

1. Rebuild CSS (`npx tailwindcss -i ./input.css -o ./output.css`).
2. Check desktop flow: hero impact, card spacing, section transitions, footer density.
3. Check mobile flow: no text clipping, no horizontal scroll, clean stack order.
4. Verify consistent heading/body font pairing (`Sora` + `Manrope`).
5. Verify all colors come from theme tokens (`blue`, `parchment`, `vibrant-coral`, `black`).

## Best Practices for AI-Assisted Development

- When adding or editing sections, maintain the current page blueprint unless the user asks for structural changes.
- For styling changes, update `input.css` or `tailwind.config.js` and rebuild.
- Suggest improvements aligned with AI/agreement-management storytelling.
- Use semantic HTML and readable section boundaries.
- If a request asks to "match screenshot closely," optimize for visual likeness first and perfect asset parity second.
