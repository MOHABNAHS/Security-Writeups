challenge name --->> Reflected XSS into HTML context with nothing encoded
---------------------------------------------
- **Bug:** The search box reflects user input directly into the HTML response without HTML encoding, allowing JavaScript execution
- **Idea of solution:** Inject a `<script>` tag to trigger an `alert()` popup in the browser
- **Solution:** `<script>alert("test alert")</script>`
- **Protection:** Convert `<` and `>` to `&lt;` and `&gt;` (HTML Encoding), or use `textContent` instead of `innerHTML` in JavaScript so the browser treats user input as plain text, not executable code