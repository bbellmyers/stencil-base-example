## Base tag without href breaks IE11

See https://github.com/ionic-team/stencil/issues/1994

In IE11, If the document has a base tag without a href attribute, the baseURI in dom.js returns undefined. This breaks hydration, and NO COMPONENTS RENDER.

For instance, this occurs if the base tag is like this:
```
<base target="_parent">
```
Storybook, for instance, has this base tag on every storybook story page.

**Expected behavior:**
baseURI should use the document's URL if no href is provided by &lt;base&gt;.
