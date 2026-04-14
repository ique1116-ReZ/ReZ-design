# ReZ Design Tokens

## 1. Typography

### Font Family
```css
/* Google Fonts: Doto */
font-family: 'Doto', -apple-system, BlinkMacSystemFont, sans-serif;
```

Font weights: 400, 500, 600, 700, 800, 900

### Type Scale
| Token | Size | Usage |
|-------|------|-------|
| --text-display | 48-64px | Hero numbers |
| --text-heading | 24-32px | Section titles |
| --text-body | 16-18px | Primary content |
| --text-label | 14px | Secondary labels |
| --text-caption | 12px | Metadata, hints |
| --text-tag | 10px | Tags, badges |

### Text Colors
```css
--text-primary: rgba(255, 255, 255, 0.88);   /* Main content */
--text-secondary: rgba(255, 255, 255, 0.45); /* Labels */
--text-muted: rgba(255, 255, 255, 0.28);     /* Hints, disabled */
```

---

## 2. Color System

### Background
```css
--bg-base: #0A0A0A;  /* Pure black base */
--bg-surface: rgba(45, 45, 45, 0.3);  /* Glass card surface */
```

### Accent Color
```css
--accent: #FFBF17;  /* Yellow - used sparingly for highlights */
```

### Status Colors
```css
--status-active: rgba(255, 191, 23, 0.15);   /* Active tag bg */
--status-border: rgba(255, 191, 23, 0.3);     /* Active tag border */
--status-text: rgba(255, 191, 23, 0.9);       /* Active tag text */
```

---

## 3. Spacing Scale

```css
--space-xs: 4px;    /* Tight groupings */
--space-sm: 8px;    /* Icon + label */
--space-md: 16px;   /* List items, form fields */
--space-lg: 24px;   /* Section gaps */
--space-xl: 32px;   /* Card padding */
--space-2xl: 48px;  /* Major sections */
```

---

## 4. Glass Effects

### Card Glass
```css
.glass-card {
  background: rgba(45, 45, 45, 0.3);
  backdrop-filter: blur(40-50px);
  -webkit-backdrop-filter: blur(40-50px);
  border-radius: 40px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow:
    inset 0 0 30px rgba(255, 255, 255, 0.03),
    inset 0 1px 0 rgba(255, 255, 255, 0.15),
    0 25px 50px rgba(0, 0, 0, 0.5);
}
```

### Inner Glow Border
```css
.glass-card::before {
  content: '';
  position: absolute;
  inset: 1px;
  border-radius: 39px;
  background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, transparent 50%);
  pointer-events: none;
}
```

---

## 5. Motion

```css
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);
--duration-fast: 150ms;
--duration-normal: 300ms;
--duration-slow: 400ms;
```
