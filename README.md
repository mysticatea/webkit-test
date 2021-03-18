# Webkit's weird behavior

[https://mysticatea.github.io/webkit-test/index.html](https://mysticatea.github.io/webkit-test/index.html)

1. `iframe.html` has a button to change URL fragment.
1. `index.html` has `<iframe>` element for `iframe.html`.
1. `index.html` subscribes the `hashchange` event of `iframe.html`.
   - It updates the URL fragment of `index.html`.

## Expected behavior

The URL fragments of `index.html` and `iframe.html` are changed.

## Actual behavior

- Chromium 90.0.4421.0 : Fine
- Firefox 86.0b10 : Fine
- Safari 14.1 : Bad - The top-level browsing context navigated to `iframe.html` for some reason.
