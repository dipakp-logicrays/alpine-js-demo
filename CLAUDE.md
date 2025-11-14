# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a comprehensive Alpine.js demo and reference project featuring 27 interactive examples for all Alpine.js v3 directives and magic properties. The project serves as both a learning resource and a complete reference for Alpine.js developers.

## Project Structure

```
alpine-js-demo/
├── index.html              # Main navigation hub with search and filtering
├── README.md               # User-facing documentation
├── CLAUDE.md               # This file - AI assistant guidance
└── demos/
    ├── directives/         # 18 directive demos
    │   ├── x-data.html
    │   ├── x-show.html
    │   ├── x-bind.html
    │   ├── x-for.html
    │   ├── x-if.html
    │   ├── x-model.html
    │   ├── x-on.html
    │   ├── x-text.html
    │   ├── x-html.html
    │   ├── x-init.html
    │   ├── x-effect.html
    │   ├── x-ref.html
    │   ├── x-cloak.html
    │   ├── x-transition.html
    │   ├── x-teleport.html
    │   ├── x-id.html
    │   ├── x-ignore.html
    │   └── x-modelable.html
    └── magics/             # 9 magic property demos
        ├── $el.html
        ├── $refs.html
        ├── $store.html
        ├── $watch.html
        ├── $dispatch.html
        ├── $nextTick.html
        ├── $root.html
        ├── $data.html
        └── $id.html
```

## Architecture & Technology Stack

### Core Technologies
- **Alpine.js v3**: Loaded via jsDelivr CDN (`https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js`)
- **Pure HTML/CSS**: No build process, no preprocessors, no bundlers
- **No external dependencies**: Everything needed is loaded from CDN or inline

### Design Principles
1. **Self-contained demos**: Each demo file is completely standalone
2. **Progressive complexity**: Examples within each demo go from simple to advanced
3. **Inline styles**: All CSS is in `<style>` tags in the `<head>` section
4. **Educational focus**: Every example includes detailed explanations
5. **Consistent structure**: All demos follow the same HTML pattern

### Alpine.js Loading
- Script tag uses `defer` attribute to ensure DOM is ready before Alpine initializes
- Components are automatically initialized when Alpine loads
- No manual initialization code needed

## Code Style & Conventions

### HTML Structure for Demo Files

Every demo file follows this consistent structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Feature Name] Demo</title>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        /* Standard styling - see CSS Conventions below */
    </style>
</head>
<body>
    <h1>[Feature Name]</h1>

    <div class="explanation">
        <strong>What is [Feature]?</strong>
        <p>[Clear explanation of the feature]</p>
    </div>

    <h2>Example 1: [Example Title]</h2>
    <div class="demo" x-data="{ /* example data */ }">
        <!-- Interactive example -->
    </div>
    <div class="explanation">
        <strong>Explanation:</strong> [How this example works]
    </div>

    <!-- More examples (typically 5-10 per demo) -->

    <a href="../../index.html">← Back to All Demos</a>
</body>
</html>
```

### CSS Conventions

**Standard Classes Used Across All Demos:**
- `.demo` - Container for interactive example (gray background, padding, rounded corners)
- `.explanation` - Blue explanation box with border-left accent
- `.box` - White box for nested content within demos
- Additional utility classes (`.s1`, `.s2`, etc.) for demo-specific styling

**Standard Styles for Demo Files:**
```css
body {
    font-family: Arial, sans-serif;
    max-width: 800px;
    margin: 50px auto;
    padding: 20px;
}
.demo {
    background: #f5f5f5;
    padding: 20px;
    margin: 20px 0;
    border-radius: 8px;
}
.explanation {
    background: #e3f2fd;
    padding: 15px;
    margin: 10px 0;
    border-left: 4px solid #2196f3;
}
button {
    padding: 10px 20px;
    margin: 5px;
    cursor: pointer;
}
input {
    padding: 8px;
    margin: 5px;
}
```

### Alpine.js Code Conventions

**x-data Declaration:**
- Simple data: Inline JSON object `x-data="{ count: 0 }"`
- Complex data: Multi-line with methods properly formatted
- Always use proper JavaScript syntax (quotes, commas, semicolons)

**Event Handlers:**
- Use `@click` shorthand instead of `x-on:click`
- Use `:class` shorthand instead of `x-bind:class`
- For keyboard events: `@keyup.enter`, `@keyup.escape`, etc.

**Data Binding:**
- Use `x-text` for safe text content (preferred for text-only)
- Use `x-html` only when HTML rendering is necessary (with security warning)
- Use `x-model` for two-way binding with form inputs

**Template Iteration:**
- Always use `:key` attribute in `x-for` loops
- Prefer `(item, index) in items` syntax for clarity
- Use `<template>` tag for `x-for` and `x-if` directives

## Development Workflow

### Viewing & Testing Demos Locally

**Start Local Server:**
```bash
# Option 1: Python (recommended)
python3 -m http.server 8000

# Option 2: PHP
php -S localhost:8000
```

**Access the Project:**
- Main index: `http://localhost:8000/`
- Direct demo access: `http://localhost:8000/demos/directives/x-data.html`

**Testing Checklist:**
- [ ] All interactive elements work as expected
- [ ] Explanations are clear and accurate
- [ ] Code examples run without errors
- [ ] Styling is consistent with other demos
- [ ] Back navigation link works correctly
- [ ] Mobile responsive (test at different screen widths)

### Adding New Demos

**Step 1: Create Demo File**
1. Create new HTML file in `demos/directives/` or `demos/magics/`
2. Use filename matching the feature name (e.g., `x-data.html`, `$el.html`)
3. Copy structure from existing demo as template
4. Maintain consistent styling and formatting

**Step 2: Update index.html**
Add entry to the appropriate array in `index.html`:

```javascript
// For directives (around line 176-195)
directives: [
    { name: 'x-newdirective', desc: 'Clear, concise description' },
    // ...
]

// For magic properties (around line 196-206)
magics: [
    { name: '$newmagic', desc: 'Clear, concise description' },
    // ...
]
```

**Step 3: Verify Integration**
- Restart local server
- Check demo appears on index page
- Test search functionality includes new demo
- Verify filtering by category works

### Modifying Existing Demos

**When to Modify:**
- Fixing bugs or errors
- Improving explanations for clarity
- Adding additional examples to enhance understanding
- Updating to reflect Alpine.js changes

**When NOT to Modify:**
- Don't change working examples unless improving them
- Don't alter the established structure and styling
- Don't remove examples without good reason
- Don't introduce external dependencies

### Maintaining Consistency

**Critical Consistency Points:**
1. **File naming**: Lowercase, match directive/magic name exactly
2. **Navigation**: Always use `../../index.html` for back links
3. **Styling**: Use established class names and CSS patterns
4. **Structure**: Follow the example > explanation pattern
5. **Alpine CDN**: Keep version consistent across all files (`3.x.x`)

## Alpine.js Key Concepts Reference

### Core Directives
- **`x-data`**: Declares component scope and reactive state (REQUIRED for all components)
- **`x-init`**: Runs code when component initializes
- **`x-show`**: Toggles visibility with CSS `display` (element stays in DOM)
- **`x-if`**: Conditionally adds/removes elements from DOM entirely
- **`x-for`**: Loops through arrays to create repeated elements
- **`x-bind` (`:`)**: Binds attributes dynamically to data
- **`x-on` (`@`)**: Attaches event listeners
- **`x-model`**: Two-way data binding for form inputs
- **`x-text`**: Sets text content safely (HTML escaped)
- **`x-html`**: Sets innerHTML (security risk - use carefully)
- **`x-transition`**: Adds CSS transitions and animations
- **`x-effect`**: Re-runs code when dependencies change
- **`x-ref`**: Creates named references to DOM elements
- **`x-cloak`**: Hides elements until Alpine initializes
- **`x-teleport`**: Moves elements to different DOM locations
- **`x-id`**: Generates unique IDs for accessibility
- **`x-ignore`**: Tells Alpine to skip element initialization
- **`x-modelable`**: Makes component properties bindable with `x-model`

### Magic Properties
- **`$el`**: References current DOM element
- **`$refs`**: Object of elements marked with `x-ref`
- **`$store`**: Global state management across components
- **`$watch`**: Watches data changes and executes callbacks
- **`$dispatch`**: Dispatches custom browser events
- **`$nextTick`**: Waits for next DOM update cycle
- **`$root`**: References root component element
- **`$data`**: Access to all component data properties
- **`$id`**: Generates unique IDs (same as `x-id`)

### Important Alpine.js Patterns

**Component Initialization:**
- Alpine automatically initializes when DOM is loaded (due to `defer`)
- Components are initialized from outside-in (parent before children)
- `x-init` runs during component initialization

**Reactivity:**
- All properties in `x-data` are reactive
- Nested objects and arrays are also reactive
- Methods can modify reactive data using `this` keyword
- DOM automatically updates when data changes

**Event Handling:**
- Use `@click`, `@input`, `@submit`, etc.
- Access event object with `$event`
- Use modifiers: `@click.prevent`, `@keyup.enter`, `@click.outside`
- Can call inline expressions or methods

**Common Modifiers:**
- `.prevent` - preventDefault()
- `.stop` - stopPropagation()
- `.outside` - trigger when clicking outside element
- `.window` - listen on window object
- `.debounce` - debounce event handler

## Git Workflow

### Branch Strategy
- **Development branch**: Work on `claude/[session-id]` branches
- **Never push to main** without explicit permission
- Create feature branches for significant changes

### Commit Guidelines
- Write clear, descriptive commit messages
- Use present tense ("Add feature" not "Added feature")
- Reference specific files/features changed
- Keep commits focused on single logical changes

### Example Good Commits
```bash
git commit -m "Add x-transition demo with 8 interactive examples"
git commit -m "Fix broken back navigation in $store demo"
git commit -m "Update CLAUDE.md with comprehensive development guide"
git commit -m "Improve explanation clarity in x-for examples"
```

## Common Tasks for AI Assistants

### ✅ DO:
- Add new demos following existing structure and patterns
- Fix bugs and errors in existing demos
- Improve explanations and documentation clarity
- Enhance examples with additional use cases
- Update CLAUDE.md when making structural changes
- Test changes locally before committing
- Maintain consistent styling across all demos
- Provide clear explanations in code and documentation

### ❌ DON'T:
- Add build tools, bundlers, or preprocessors
- Install npm packages or create package.json
- Add external CSS frameworks or libraries
- Change the fundamental structure without discussion
- Remove working examples without good reason
- Modify Alpine.js version without testing thoroughly
- Create overly complex examples that confuse beginners
- Add examples that don't follow security best practices

## Security Considerations

### x-html Usage
- Use `x-html` only when absolutely necessary
- Always sanitize user input before rendering with `x-html`
- Prefer `x-text` for displaying user-generated content
- Include warnings in demos that use `x-html`

### Event Handlers
- Avoid inline `eval()` or `Function()` constructors
- Don't execute arbitrary user input as code
- Use proper event modifiers to prevent default behaviors

### Data Validation
- Validate form inputs in examples
- Show proper error handling patterns
- Demonstrate safe data manipulation

## Troubleshooting Common Issues

### Alpine Not Initializing
- Check script tag has `defer` attribute
- Verify CDN URL is correct and accessible
- Ensure no JavaScript errors in console
- Check `x-data` is properly defined on parent element

### Reactivity Not Working
- Verify property is defined in `x-data` object
- Check for typos in property names
- Ensure using `this` keyword in methods
- Remember nested objects are reactive but reassignment may be needed

### Styling Issues
- Verify CSS classes are defined in `<style>` section
- Check for conflicting class names
- Ensure proper CSS specificity
- Test in multiple browsers if issues persist

### Demo Navigation
- Verify back link is `../../index.html` (two levels up)
- Check file paths are correct in index.html arrays
- Ensure filename matches exactly what's referenced

## Resources

### Alpine.js Documentation
- [Official Docs](https://alpinejs.dev)
- [GitHub Repository](https://github.com/alpinejs/alpine)

### This Project
- See README.md for user-facing documentation
- See individual demo files for implementation examples
- index.html demonstrates advanced Alpine patterns in action

## Questions?

If you're unsure about:
- **Structure**: Look at existing demo files for reference
- **Styling**: Copy CSS patterns from similar demos
- **Alpine patterns**: Check multiple demos to see consistent approaches
- **New features**: Ask before making significant architectural changes

---

**Last Updated**: 2025-11-14
**Alpine.js Version**: 3.x
**Total Demos**: 27 (18 directives + 9 magic properties)
