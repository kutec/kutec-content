---
title: How to Set Up Tailwind CSS v4 with Vite and React (Step-by-Step Guide)
cover: ""
date: "2025-08-24"
category: reactjs
slug: tailwind-css-v4-vite-react-setup-guide
tags:
  - react-beginner
  - beginner
  - tailwindcss
  - css-framework


----------


  - developer-productivity
---

If you’ve tried wiring up Tailwind CSS v4 inside a brand-new Vite + React app, chances are you’ve hit some roadblocks.  I certainly did.  The docs cover a lot, but when you’re juggling Vite’s quirks, React’s setup, and Tailwind’s new version, things can get messy fast.  
  
Most tutorials floating around (and yes, even a bunch of AI-generated ones) are stuck in the Tailwind v3 world.  That’s the catch.  Version 4 changes just enough to break all those “copy–paste this config” guides, and suddenly you’re staring at errors instead of a running dev server.  
  
After a couple of experiments (and a few “why isn’t this working?!” moments), I finally landed on a setup that actually works.  Here’s a straightforward walkthrough so you don’t waste the same time.

## Where Devs (and Bots) Usually Go Wrong

The main issue isn’t Tailwind itself—it’s the outdated instructions out there. Common mistakes include:

-   Installing `@tailwindcss/postcss` (you don’t need it anymore).    
-   Creating a `postcss.config.js` file (also unnecessary).    
-   Using the old `@tailwind` directives instead of the new `@import`.
    

If you’ve been following any v3 tutorial or AI snippet, that’s probably where things went sideways.

## The Setup (Step by Step)

### 1. Spin up your Vite + React app

```bash
npm create vite@latest my-app -- --template react
cd my-app
npm install
```

### 2. Install the right Tailwind v4 packages
```bash
npm install -D tailwindcss@latest @tailwindcss/vite@latest
```
-   `tailwindcss@latest`: the core engine.    
-   `@tailwindcss/vite@latest`: the official Vite plugin that quietly handles all the messy integration.
    

### 3. Update your Vite config
In `vite.config.js`:
```js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [react(), tailwindcss()],
})
```
Notice: no PostCSS config needed.

### 4. Add your CSS entry

Create `src/index.css` with:
```css
@import "tailwindcss";
```
That’s literally it. One line.

### 5. Hook it into your app
In `src/main.jsx`:
```jsx
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>
)
```

### 6. Fire it up
```bash
npm run dev
```

### 7. Final Step - Test
Drop a Tailwind class into your `App.jsx` and confirm it’s working:
```jsx
function App() {
  return (
    <div className="grid min-h-screen place-items-center bg-gradient-to-br from-blue-400 to-purple-600">
      <h1 className="text-6xl font-bold text-white drop-shadow-2xl">
        Success! Tailwind v4 + Vite is alive 🎉
      </h1>
    </div>
  )
}
```

## Quick Troubleshooting

-   **`Cannot find module '@tailwindcss/vite'`** → reinstall with `npm install -D @tailwindcss/vite@latest`.
    
-   **No styles showing up** → double-check that `index.css` is imported in `main.jsx`.
    
-   **Do I need a `tailwind.config.js` file?** → Not unless you’re customizing. For most projects, v4 is “zero-config.” If you want to extend the theme, just run `npx tailwindcss init`.

## Wrapping Up

The leap from Tailwind v3 to v4 actually makes life easier once you know the new rules. The `@tailwindcss/vite` plugin removes all the PostCSS clutter and lets you get straight to styling.

Hopefully, this saves you the trial-and-error loop I went through. If you’re migrating from v3, just remember: skip the old configs, trust the plugin, and you’ll be up and running in minutes.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU1ODYxNDEzXX0=
-->