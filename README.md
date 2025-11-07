# Alpine.js Complete Reference

A comprehensive collection of interactive demos for all Alpine.js v3 directives and magic properties.

## 📚 What's Inside

- **18 Directive Demos** - Every Alpine.js directive explained with multiple examples
- **9 Magic Property Demos** - All magic properties ($el, $refs, $store, etc.)
- **27 Total Interactive Demos** - Learn by doing with live, editable examples
- **Search & Filter** - Quickly find what you need
- **Beautiful UI** - Modern, responsive design

## 🚀 Quick Start

1. Start a local server:
   ```bash
   python3 -m http.server 8000
   # or
   php -S localhost:8000
   ```

2. Open your browser to `http://localhost:8000/`

3. Start exploring! Click any demo card to see interactive examples.

## 📖 Directives Covered

- **x-data** - Component data and reactivity
- **x-init** - Initialization hooks
- **x-show** - Visibility toggling
- **x-bind** - Attribute binding (`:` shorthand)
- **x-on** - Event handling (`@` shorthand)
- **x-text** - Text content (HTML-safe)
- **x-html** - HTML content rendering
- **x-model** - Two-way data binding
- **x-modelable** - Custom component binding
- **x-for** - List rendering and loops
- **x-transition** - CSS transitions and animations
- **x-effect** - Reactive side effects
- **x-ignore** - Skip Alpine initialization
- **x-ref** - DOM element references
- **x-cloak** - Hide until initialized
- **x-teleport** - Portal elements to other DOM locations
- **x-if** - Conditional rendering (removes from DOM)
- **x-id** - Unique ID generation for accessibility

## ✨ Magic Properties Covered

- **$el** - Current DOM element reference
- **$refs** - Access x-ref marked elements
- **$store** - Global state management
- **$watch** - Watch data changes
- **$dispatch** - Custom event dispatching
- **$nextTick** - Wait for DOM updates
- **$root** - Component root element
- **$data** - Component data object
- **$id** - Generate unique IDs

## 🎯 Features

Each demo includes:
- **Multiple examples** (5-10 per concept) showing different use cases
- **Detailed explanations** after each example
- **Interactive elements** - try everything live
- **Clean, consistent styling**
- **Easy navigation** between demos

## 📁 Project Structure

```
alpinejs/
├── index.html              # Main navigation hub
├── demos/
│   ├── directives/         # 18 directive demos
│   │   ├── x-data.html
│   │   ├── x-show.html
│   │   └── ...
│   └── magics/            # 9 magic property demos
│       ├── $el.html
│       ├── $refs.html
│       └── ...
├── CLAUDE.md              # Development documentation
└── README.md              # This file
```

## 🛠️ Technology

- **Alpine.js v3** - Loaded from jsDelivr CDN
- **Pure HTML/CSS** - No build process required
- **Self-contained** - Each demo works independently

## 📝 License

Free to use for learning and reference.

## 🔗 Resources

- [Alpine.js Official Documentation](https://alpinejs.dev)
- [Alpine.js GitHub](https://github.com/alpinejs/alpine)

---

**Built for developers learning Alpine.js** 🏔️
