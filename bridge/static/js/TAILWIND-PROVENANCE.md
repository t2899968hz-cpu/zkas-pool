# Tailwind dashboard runtime provenance

- File: `bridge/static/js/tailwind.js`
- Source: `https://cdn.tailwindcss.com` (Tailwind Play CDN build)
- Retrieved: 2026-11-16
- SHA-256: `176e894661aa9cdc9a5cba6c720044cbbf7b8bd80d1c9a142a7c24b1b6c50d15` (407,279 bytes)
- License: MIT (Tailwind Labs, https://github.com/tailwindlabs/tailwindcss)

The runtime is vendored so the operator dashboard loads no third-party
JavaScript. `index.html` and `raw.html` enforce `script-src 'self'` and load
only `static/js/tailwind.js` and the dashboard scripts.

Verify with:

```sh
cd bridge/static/js && shasum -a 256 -c tailwind.js.sha256
```

To update, fetch the upstream build, replace `tailwind.js`, record the new
hash here and in `tailwind.js.sha256`, and re-run the checksum verification.
