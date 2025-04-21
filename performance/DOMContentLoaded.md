# DOMContentLoaded

The DOMContentLoaded event is triggered when the initial HTML document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading. This is an important performance metric because it represents when the browser can start rendering the page and executing JavaScript that interacts with the DOM.

```js
document.addEventListener("DOMContentLoaded", function () {
  // Code to execute when the HTML document is fully loaded and parsed
  console.log("DOMContentLoaded");
});
```

[sandbox-js: document/events/load-events.html](https://github.com/uicoded/sandbox-js/blob/main/src/document/events/load-events.html)

---

## React Notes
Short answer:
- In react app, this runs **as soon as the HTML is parsed** — before any React component mounts or renders.

Long answer:
- It typically fires after the main JavaScript bundle (including React) is executed but before React completes its initial render. The exact timing depends on whether the script is loaded synchronously, async, or defer
- In most React apps, you don’t need to rely on `DOMContentLoaded` because React abstracts DOM manipulation. Instead, use React lifecycle methods (e.g., useEffect in functional components) or hooks to run code after the component mounts.
- If you’re using server-side rendering (SSR) or static site generation (SSG) with frameworks like Next.js, the `DOMContentLoaded` event still fires when the browser finishes parsing the initial HTML, but React (or Next.js) may hydrate the DOM afterward.
