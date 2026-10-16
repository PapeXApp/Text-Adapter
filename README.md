# Text Adapter

A small static page, served by GitHub Pages, that Nico's Notebook uses to open apps on his phone. The Notebook runs inside Claude, which can't open sms: or ms-outlook:// links itself, so it opens this page and the page hands off to the app.

- `go.html#app=sms&to=...&body=...` opens Messages to that number with the text filled in.
- `go.html#app=whatsapp&to=...&body=...` opens WhatsApp the same way.
- `go.html#app=outlook` opens Outlook.
- `go.html#app=share&title=...&body=...` shows a Share button that opens the phone's share sheet with the text (falls back to copying).
- Any other value shows "Nothing to open." Only these three destinations are allowed, so it can't be used as an open redirect.

Everything rides in the URL #fragment, which browsers never send to a server, so no phone number or message ever reaches GitHub. Values are built with encodeURIComponent, so a "+" country code arrives as %2B.

This repo is public. Never put notes, keys, contacts or anything private here.
