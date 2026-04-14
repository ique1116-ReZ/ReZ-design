# Platform Output Conventions

## HTML/CSS (Primary)

### Font Loading
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Doto:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
```

### Base Setup
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>App Name</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Font link above -->
  <style>
    * {
      -webkit-tap-highlight-color: transparent;
    }
    body {
      font-family: 'Doto', -apple-system, BlinkMacSystemFont, sans-serif;
      background: #0A0A0A;
      /* Optional subtle light sources */
      background:
        radial-gradient(ellipse 80% 50% at 20% 20%, rgba(60, 60, 60, 0.15) 0%, transparent 50%),
        radial-gradient(ellipse 60% 40% at 80% 80%, rgba(50, 50, 50, 0.12) 0%, transparent 50%),
        #0A0A0A;
    }
  </style>
</head>
```

### Scrollbar Hide
```css
::-webkit-scrollbar { width: 0; }
```

### Safe Area (Mobile)
```css
.safe-bottom {
  padding-bottom: max(24px, env(safe-area-inset-bottom));
}
```

---

## Tailwind CSS Usage

When using Tailwind, extend the config:

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      fontFamily: {
        'doto': ['Doto', '-apple-system', 'BlinkMacSystemFont', 'sans-serif'],
      },
      colors: {
        'accent': '#FFBF17',
        'surface': 'rgba(45, 45, 45, 0.3)',
        'text-primary': 'rgba(255, 255, 255, 0.88)',
        'text-secondary': 'rgba(255, 255, 255, 0.45)',
        'text-muted': 'rgba(255, 255, 255, 0.28)',
      },
      backdropBlur: {
        'glass': '40px',
      },
      borderRadius: {
        'glass': '40px',
      },
    },
  },
}
```

---

## Component Class Mapping

| Component | Tailwind Classes |
|-----------|-----------------|
| Glass Card | `glass-card bg-surface backdrop-blur-[40px] border border-white/10` |
| Glass Card Strong | `glass-card-strong bg-surface backdrop-blur-[50px] border border-white/12` |
| Tag | `inline-flex items-center gap-1 px-3 py-1 rounded-lg border border-white/10 bg-white/5 text-white/50 text-[10px]` |
| Tag Active | `bg-accent/15 border-accent/30 text-accent` |
| Floating Tabs | `flex gap-1 p-1 bg-neutral-800/60 backdrop-blur-[20px] rounded-2xl border border-white/8` |
| Tab Active | `px-5 py-2.5 rounded-2xl bg-white/92 text-black font-semibold` |
| Stat Card | `bg-neutral-800/40 backdrop-blur-[20px] rounded-3xl border border-white/6 p-5` |
| Bottom Nav | `fixed bottom-0 left-0 right-0 bg-neutral-900/85 backdrop-blur-[30px] border-t border-white/5` |

---

## CSS Custom Properties

For reusable tokens in CSS:

```css
:root {
  --accent: #FFBF17;
  --bg-base: #0A0A0A;
  --bg-surface: rgba(45, 45, 45, 0.3);
  --text-primary: rgba(255, 255, 255, 0.88);
  --text-secondary: rgba(255, 255, 255, 0.45);
  --text-muted: rgba(255, 255, 255, 0.28);
  --radius-glass: 40px;
  --blur-glass: blur(40px);
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
}
```
