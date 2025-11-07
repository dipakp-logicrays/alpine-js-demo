# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a comprehensive Alpine.js demo and reference project featuring interactive examples for all Alpine.js directives and magic properties.

## Project Structure

- **`index.html`**: Main navigation hub with search and categorization
- **`demos/` directory**: Complete reference with 27 interactive demos
  - `demos/directives/`: 18 directive demos (x-data, x-show, x-bind, x-for, etc.)
  - `demos/magics/`: 9 magic property demos ($el, $refs, $store, $watch, etc.)
- **`CLAUDE.md`**: This file - development documentation

## Architecture

- **No build process**: Pure HTML/CSS with Alpine.js v3 from CDN
- **Alpine.js v3**: Loaded via CDN (`https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js`)
- **Self-contained demos**: Each demo is standalone with explanations and multiple examples

## Development Workflow

**Viewing the demos:**
- Start a local server: `python3 -m http.server 8000` or `php -S localhost:8000`
- Navigate to `http://localhost:8000/` to see the main demo index
- Browse by category (Directives/Magic Properties) or use search
- Each demo is interactive and includes multiple examples with detailed explanations

**Adding new demos:**
- Create new HTML file in `demos/directives/` or `demos/magics/`
- Follow existing demo structure (header, explanations, multiple examples)
- Update `index.html` to include the new demo in the `directives` or `magics` arrays
- Ensure "Back to All Demos" link points to `../../index.html`

## Alpine.js Key Concepts

When adding Alpine.js functionality, remember:
- `x-data` defines component scope and reactive state
- `x-model` creates two-way data binding
- `x-text` and `x-html` for content rendering
- `x-show` and `x-if` for conditional rendering
- `x-on:` (or `@`) for event handling
- `x-bind:` (or `:`) for attribute binding
- Alpine components are initialized when the DOM is loaded (defer script ensures this)
