---
sidebar_position: 1
---

# The `script` tag

- JavaScript programs can be inserted almost anywhere into an HTML document using the `script` tag.
- The `script` tag contains JavaScript code which is **automatically executed when the browser processes the tag.**

```html
<html>
  <body>
    <p>Before the script...</p>
    // highlight-start
    <script>
      alert("Hello, world!");
    </script>
    // highlight-end
    <p>...After the script.</p>
  </body>
</html>
```

## Attributes

### 1. `src` (Source)

- If we have a lot of JavaScript code, we can put it into a separate file.
- Script files are attached to HTML with the `src` attribute:
- This attribute specifies the source URL of an external JavaScript file that should be loaded and executed.

**Relative path**

```html
<script src="/path/to/script.js"></script>
```

**Full URL**

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js"></script>
```

:::tip

- As a rule, only the simplest scripts are put into HTML. More complex ones reside in separate files.

- The benefit of a separate file is that the **browser will download it and store it in its cache.**

- Other pages that reference the same script will take it from the cache instead of downloading it, so the file is actually downloaded only once.

- That reduces traffic and makes pages faster.

:::

### 2. `type`

- The `type` attribute specifies the MIME type of the script. For JavaScript, the value should be "text/javascript."
- However, this attribute is <b>not required in HTML5 because JavaScript is assumed by default.</b>

```html
<script type="text/javascript">
  // JavaScript code here
</script>
```

### 3. `async`

- **The `async` attribute is a Boolean attribute** that indicates whether the script should be executed asynchronously.
- When set to "async," the script will not block the loading of other elements on the page and **will execute as soon as it's available.** This is often used for non-blocking script loading.

```html
<script src="myscript.js" async></script>
```

### 4. `defer`

- **The `defer` attribute is a Boolean attribute** that indicates that the script should be **executed after the HTML document is fully parsed.**
- Multiple deferred scripts will **execute in the order they appear** in the HTML document.

```html
<script src="myscript.js" defer></script>
```

### 5. `integrity`

- This attribute is used in conjunction with the `src` attribute to ensure the integrity and authenticity of an external script. It contains a cryptographic hash of the script's content. This helps protect against potential tampering or CDN issues.

```html
<script
  src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js"
  integrity="sha384-HwwvtgBNo3bZJJLYd8oVXjrBZt8cqVSpeBNS5n7C8IVInixGAoxmnlMuBnhbgrkm"
  crossorigin="anonymous"
></script>
```

### 6. `crossorigin`

- The `crossorigin` attribute is used when loading scripts from a different domain. It can have values like "anonymous" or "use-credentials" to control how cross-origin requests are handled.

```html
<script src="https://example.com/myscript.js" crossorigin="anonymous"></script>
```

These attributes provide control and flexibility when including JavaScript in your HTML documents, allowing you to manage script loading, execution, and security considerations. Depending on your specific use case and requirements, you may choose to use one or more of these attributes in your `<script>` tags.
