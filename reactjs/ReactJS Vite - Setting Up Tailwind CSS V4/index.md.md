---
title: Why AI Still Messes Up Tailwind CSS v4 + Vite — And How You Can Get It Right in One Go
cover: ""
date: "2025-08-24"
category: reactjs
slug: reactjs-vite-tailwindcssv4-setup
tags:
  - react-beginner
  - beginner
  - tailwindcss
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

`npm create vite@latest my-app -- --template react cd my-app
npm install` 

### 2. Install the right Tailwind v4 packages

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMzMzMzY3MiwyMDE2Nzk1MzYyXX0=
-->