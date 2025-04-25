# How I Learned Web Components the Hard Way (And Why You Should Too)

Hey there! 👋 I’m Kushal, a frontend developer from India, who spent  **way too long**  relying on React for everything—until I discovered HTML5 Web Components.

Here’s the story of how I went from  _"This looks complicated"_  to  _"Why didn’t I learn this sooner?!"_—including my mistakes, lightbulb moments, and how you can skip the frustrating parts.

## 1. My "Aha!" Moment

**The Problem:**  
Back in 2022, I was building a marketing site with **three identical card components**. 

My React solution:
```
// Card.jsx  
export default function Card({ title }) {  
  return <div className="card">{title}</div>;  
}  
```
It worked, but:

-   **🚀 45KB of React + hydration**  just for static cards
    
-   **🤯 Overkill**  for a simple website
    

**The Wake-Up Call:**  
My coworker casually mentioned:  _"You know browsers already support component reuse, right?"_

Cue my existential crisis.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEyMTYyMjJdfQ==
-->