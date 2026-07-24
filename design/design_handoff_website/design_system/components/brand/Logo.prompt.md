Renders the ATTIA Consulting logo — a type-based wordmark (always safe) that can be paired with the network-of-people mark. Use in headers, footers, cover slides, and stationery.

```jsx
<Logo markSrc="assets/attia-logo.png" size={44} />
<Logo variant="wordmark" tone="light" size={32} />
<Logo variant="stacked" markSrc="assets/attia-logo.png" />
```

Variants: `lockup` (mark left of wordmark, default), `wordmark` (type only), `stacked` (mark above). `tone="light"` reverses for dark grounds. `markSrc` is optional — without it you get a dependency-free type lockup.
