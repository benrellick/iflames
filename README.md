## iflames (an iframework)

This is the first completely iframe-based framework.
- **css-in-iframe** - Scoped CSS out of the box (kick rocks, :scope)
- **Proven** - Well established industry standard (1997 - ?)
- **Fast** - Lightweight, ships very little JS (i.e. absolutely none)
- **Reusable components** - Provides a composable, atomic design via nesting iframes inside of other iframes using the `srcdoc` attribute
- **#usetheplatform** - Standards compliant, web native, and a complete pain in the ass to use (you chose to walk this path, not me)
- **Equitable** - Accessible, or at least not inaccessible

## Project roadmap
- Supercharge the iframe via a web component, tentatively titled either `<better-iframe>` or `<this-iframe-fucks>`
- Reinvent the wheel by reimplementing `useSignal()` via `postMessage()`
- Use CSS custom properties to pass props. Can an iframe within an iframe even *read* CSS custom properties from the parent element? tbh, I don't know if anyone has ever had motivation misguided enough to try.

## Getting Started
An example of what a standard page might look like:

```
<!-- Text in the parent element is unaffected by styles within components --> 
<p>Text outside the iframe</p>

<iframe width="500px" height="500px" srcdoc="

  <iframe srcdoc='
    <h1>Heading</h1>
    <style>
      h1 {
        color: red;
      }
    </style>
  '></iframe>

  <iframe srcdoc='
    <p>Text inside the iframe</p>
    <style>
      /* Styles scoped only to p elements within this iframe */
      p {
        color: blue;
      }
    </style>
  '></iframe>

  <iframe srcdoc='
    <button>CTA</button>
    <style>
      button {
        background: pink;
      }
    </style>
  '></iframe>

"></iframe>
```

