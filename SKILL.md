---
name: ReZ
description: Creates immersive dark glassmorphism UIs with frosted glass effects and subtle inner glow borders. Use when building mobile apps, dashboards, or interfaces requiring premium dark theme with heavy blur glass, floating tabs, or status indicators. Every time user mentions dark mode UI, glassmorphism, mobile app design, dark luxury theme, or premium dark interfaces - invoke this skill. Triggers for: dark glassmorphism, ReZ style UI, dark luxury design, premium dark mobile app.
version: 1.0.0
allowed-tools: [Read, Write, Edit, Glob, Grep]
---

# ReZ Design System

沉浸式暗色毛玻璃设计系统。打造具有重型模糊、边缘微光和奢华质感的移动端界面。

**Before starting any design work, declare which Google Fonts are required** (see `references/platform-mapping.md` Section 1).

---

## 1. Design Philosophy

- **Dark luxury.** 纯黑色背景配合微妙光晕折射，营造沉浸式深色氛围。
- **Heavy glass.** 重型模糊（40-50px）模拟真实毛玻璃材质。
- **Inner glow.** 边缘内发光边框创造3D厚度感。
- **Minimal accent.** 黄色（#FFBF17）仅用于重点强调。
- **Smooth motion.** 使用 cubic-bezier 缓动，过渡自然流畅。

---

## 2. Visual Hierarchy

Every screen follows **three layers of importance:**

| Layer | What | How |
|-------|------|-----|
| **Primary** | Key metric, hero number | Doto at 48-64px, --text-primary |
| **Secondary** | Labels, descriptions | Doto at 14-16px, --text-secondary |
| **Tertiary** | Metadata, hints | Doto at 10-12px, --text-muted |

---

## 3. Color System

| Token | Value | Usage |
|-------|-------|-------|
| Background | #0A0A0A | Base background |
| Surface | rgba(45, 45, 45, 0.3) | Glass card bg |
| Accent | #FFBF17 | Highlights, status |
| Text Primary | rgba(255, 255, 255, 0.88) | Main content |
| Text Secondary | rgba(255, 255, 255, 0.45) | Labels |
| Text Muted | rgba(255, 255, 255, 0.28) | Hints |

---

## 4. Component Usage

### Glass Card
```css
.glass-card {
  background: rgba(45, 45, 45, 0.3);
  backdrop-filter: blur(40-50px);
  border-radius: 40px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow:
    inset 0 0 30px rgba(255, 255, 255, 0.03),
    inset 0 1px 0 rgba(255, 255, 255, 0.15),
    0 25px 50px rgba(0, 0, 0, 0.5);
}
```

### Tags
- Use **small rounded rectangles** (border-radius: 8px), NOT pills
- Yellow accent for active/important states

### Floating Tabs
- Glassmorphic container with backdrop blur
- White solid for active, transparent for inactive

### Status Dots
- Yellow (#FFBF17) with subtle glow shadow
- 6px circular indicator

---

## 5. Animation

```css
--ease-out: cubic-bezier(0.16, 1, 0.3, 1);
--duration-fast: 150ms;
--duration-normal: 300ms;
--duration-slow: 400ms;
```

**Rules:**
- Animate only compositor-friendly properties: opacity, transform
- Avoid animating layout-bound properties (width, height, margin, padding)
- Use ease-out or custom cubic-bezier

---

## 6. Workflow

1. **Declare fonts** — tell user to load Doto from Google Fonts
2. **Apply base styles** — #0A0A0A background, glass-card for surfaces
3. **Build hierarchy** — 3 layers (primary, secondary, tertiary)
4. **Add components** — consult `references/components.md` for specs
5. **Check tokens** — consult `references/tokens.md` for exact values
6. **Map output** — consult `references/platform-mapping.md` for conventions

---

## 7. Reference Files

| File | Content |
|------|---------|
| `references/tokens.md` | Fonts, colors, spacing, glass effects |
| `references/components.md` | All UI component specifications |
| `references/platform-mapping.md` | HTML/CSS, Tailwind output conventions |
