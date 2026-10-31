# music.sankhacooray.com

Single-file site (`index.html`, all CSS/JS inline) on GitHub Pages: pushing `main` deploys. See README.md.
Videos use a click-to-load YouTube facade: the poster is a local WebP in `thumbs/yt-<id>.webp`
(16:9 crop of the YouTube thumbnail); add new videos the same way rather than embedding an iframe.

## Lighthouse
<!-- lighthouse-optimized: 2026-10-31 -->
Baseline (mobile): performance 56, accessibility 100, best-practices 96, SEO 100.
Fixed: the two YouTube iframes (~2 MB of player JS, Roboto without font-display, third-party cookie issues) became click-to-play facades with local WebP posters; Google Fonts load non-blocking with preconnects; project thumbnails and the FL Studio logo served as WebP (logo resized to 52px and lazy).
Left: the screen-fit layout's forced reflow is inherent to measuring section heights (already batched in one rAF); gtag/shared-script findings handled centrally; GitHub Pages can't set cache headers. Original JPG thumbs are kept in case other sites link to them.
