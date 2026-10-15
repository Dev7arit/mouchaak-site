MOUCHAAK.COM — site package
===========================

What is in this folder
  index.html            the whole site in one file (HTML, CSS and JavaScript, no build step)
  three.min.js          the 3D rendering library used by the hero and the About section (self-hosted, no CDN needed)
  og-image.png          social preview image (1200 x 630) used by LinkedIn, WhatsApp, X, Slack
  favicon.svg           browser-tab icon (modern browsers)
  favicon-32.png        browser-tab icon fallback
  favicon-192.png       Android home-screen icon
  apple-touch-icon.png  iPhone / iPad home-screen icon

Deploying
  Upload every file to the root of your web host so that index.html is served at https://mouchaak.com/.
  Works on any static host: Netlify, Vercel, Cloudflare Pages, GitHub Pages, or cPanel / shared hosting.
  Make sure the site is served over HTTPS; the canonical URL in the file is https://mouchaak.com/.

Contact form
  Out of the box the form composes an email to hello@mouchaak.com (the visitor opens it in their mail app
  or copies the message). To receive submissions without email, create a form endpoint
  (Formspree, Web3Forms, Basin, or your own API) and paste its URL into
      <form class="form" id="contact-form" novalidate data-endpoint="">
  in index.html. The page then POSTs JSON with the fields name, email, company, need and message.
  To change the contact address, search index.html for hello@mouchaak.com (it appears a few times).

Editing content
  All copy is plain HTML and can be edited in any text editor.
  The turnaround chart's example numbers live in the `rows` array near the end of index.html.
  The hero console's example runs live in the `jobs` array in the same script block.
  The footer line "A Kajkarma company" can be removed by deleting that <span> in the footer.

Fonts
  Loaded from Google Fonts (Fraunces, Hanken Grotesk, IBM Plex Mono).
  To self-host them later, replace the <link rel="stylesheet" href="https://fonts.googleapis.com/..."> tag
  with @font-face rules pointing at font files on your server.

3D scenes
  The hero field and the About "hive core" are rendered with WebGL. On devices without WebGL the hero falls
  back to a flat honeycomb drawing and the hive core is hidden, so the page still works everywhere.
  Visitors who have "reduce motion" switched on see a single still frame instead of the animation.
  Keep three.min.js next to index.html; the page loads it with a relative path.