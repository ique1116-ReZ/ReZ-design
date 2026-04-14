# ReZ UI Components

## 1. Glass Card

### Primary Glass Card
```css
.glass-card {
  position: relative;
  background: rgba(45, 45, 45, 0.3);
  backdrop-filter: blur(40-50px);
  -webkit-backdrop-filter: blur(40-50px);
  border-radius: 40px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow:
    inset 0 0 30px rgba(255, 255, 255, 0.03),
    inset 0 1px 0 rgba(255, 255, 255, 0.15),
    0 25px 50px rgba(0, 0, 0, 0.5);
  overflow: hidden;
}

.glass-card::before {
  content: '';
  position: absolute;
  inset: 1px;
  border-radius: 39px;
  background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, transparent 50%);
  pointer-events: none;
}
```

### Strong Glass Card (for featured content)
```css
.glass-card-strong {
  background: rgba(45, 45, 45, 0.3);
  backdrop-filter: blur(50px);
  -webkit-backdrop-filter: blur(50px);
  border-radius: 40px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  box-shadow:
    inset 0 0 40px rgba(255, 255, 255, 0.04),
    inset 0 1px 0 rgba(255, 255, 255, 0.2),
    inset 0 -1px 0 rgba(0, 0, 0, 0.2),
    0 30px 60px rgba(0, 0, 0, 0.5);
}

.glass-card-strong::before {
  background: linear-gradient(135deg, rgba(255,255,255,0.12) 0%, transparent 40%, transparent 60%, rgba(255,255,255,0.05) 100%);
}
```

---

## 2. Tags

### Base Tag
```css
.tag {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 4px 10px;
  border-radius: 8px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  background: rgba(255, 255, 255, 0.05);
  font-size: 0.7rem;
  font-weight: 500;
  letter-spacing: 0.02em;
  color: rgba(255, 255, 255, 0.5);
}
```

### Active Tag
```css
.tag-active {
  background: rgba(255, 191, 23, 0.15);
  border-color: rgba(255, 191, 23, 0.3);
  color: rgba(255, 191, 23, 0.9);
}
```

### Warning Tag
```css
.tag-warning {
  background: rgba(255, 191, 23, 0.12);
  border-color: rgba(255, 191, 23, 0.25);
  color: rgba(255, 191, 23, 0.8);
}
```

---

## 3. Floating Tabs

### Tab Container
```css
.floating-tabs {
  display: flex;
  gap: 4px;
  padding: 4px;
  background: rgba(30, 30, 30, 0.6);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-radius: 20px;
  border: 1px solid rgba(255, 255, 255, 0.08);
}
```

### Tab Button
```css
.tab {
  padding: 10px 18px;
  border-radius: 16px;
  font-size: 0.8rem;
  font-weight: 500;
  transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
  cursor: pointer;
}

.tab-active {
  background: rgba(255, 255, 255, 0.92);
  color: #0A0A0A;
  font-weight: 600;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

.tab-inactive {
  background: transparent;
  color: rgba(255, 255, 255, 0.35);
}
```

---

## 4. Status Dots

```css
.status-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
}

.status-dot-active {
  background: #FFBF17;
  box-shadow: 0 0 8px rgba(255, 191, 23, 0.6);
}
```

---

## 5. Checkbox (Round)

### CSS
```css
.container input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
  display: none;
  color: white;
}

.container {
  --size: 50px;
  width: var(--size);
  display: block;
  height: var(--size);
  background-color: #FFBF17;
  border-radius: 100%;
  cursor: pointer;
  padding: 5px;
  color: rgb(81, 75, 75);
  box-shadow:
    1.5px 1.5px 3px #0e0e0e,
    -1.5px -1.5px 3px rgb(95 94 94 / 25%),
    inset 0px 0px 0px #0e0e0e,
    inset 0px -0px 0px #5f5e5e;
}

.container .checkmark {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  box-shadow:
    1.5px 1.5px 3px #0e0e0e,
    -1.5px -1.5px 3px rgb(95 94 94 / 25%),
    inset 0px 0px 0px #0e0e0e,
    inset 0px -0px 0px #5f5e5e;
  transition: all ease 0.3s;
  padding: 8px;
}

.container .checkmark svg {
  opacity: 0;
  transition: all ease 0.3s;
}

.container input:checked + .checkmark {
  box-shadow:
    0px 0px 0px #0e0e0e,
    0px 0px 0px rgb(95 94 94 / 25%),
    inset 1.5px 1.5px 3px #0e0e0e,
    inset -1.5px -1.5px 3px #5f5e5e;
}

.container input:checked + .checkmark svg {
  opacity: 1;
}
```

### HTML
```html
<label class="container">
  <input type="checkbox">
  <span class="checkmark">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3">
      <polyline points="20 6 9 17 4 12"></polyline>
    </svg>
  </span>
</label>
```

---

## 6. Toggle Switch (iOS Style)

### CSS
```css
.cl-toggle-switch {
  position: relative;
  display: inline-block;
}

.cl-toggle-switch input {
  opacity: 0;
  width: 0;
  height: 0;
  position: absolute;
}

.cl-slider {
  position: relative;
  display: block;
  width: 51px;
  height: 31px;
  background: rgba(255, 255, 255, 0.15);
  border-radius: 16px;
  cursor: pointer;
  transition: background 0.3s cubic-bezier(0.16, 1, 0.3, 1);
}

.cl-slider::before {
  content: "";
  position: absolute;
  width: 27px;
  height: 27px;
  background: #fff;
  border-radius: 50%;
  top: 2px;
  left: 2px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1);
}

.cl-toggle-switch input:checked + .cl-slider {
  background: #FFBF17;
}

.cl-toggle-switch input:checked + .cl-slider::before {
  transform: translateX(20px);
}
```

### HTML
```html
<label class="cl-toggle-switch">
  <input type="checkbox">
  <span class="cl-slider"></span>
</label>
```

---

## 7. Bottom Navigation

```css
.bottom-nav {
  background: rgba(20, 20, 20, 0.85);
  backdrop-filter: blur(30px);
  -webkit-backdrop-filter: blur(30px);
  border-top: 1px solid rgba(255, 255, 255, 0.05);
}

.nav-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  padding: 8px 20px;
  color: rgba(255, 255, 255, 0.3);
  transition: all 0.3s ease;
}

.nav-item-active {
  color: rgba(255, 255, 255, 0.85);
}
```

---

## 8. Stat Card

```css
.stat-card {
  background: rgba(35, 35, 35, 0.4);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-radius: 24px;
  border: 1px solid rgba(255, 255, 255, 0.06);
  padding: 20px;
  box-shadow: inset 0 0 20px rgba(255, 255, 255, 0.02);
}
```

---

## 9. Progress Ring

```css
.progress-ring {
  transform: rotate(-90deg);
}

.progress-ring-circle {
  transition: stroke-dashoffset 0.8s cubic-bezier(0.16, 1, 0.3, 1);
}
```
