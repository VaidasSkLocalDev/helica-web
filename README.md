# helica-web

Static pages for Helica, served via GitHub Pages at https://helica.lt.

- `index.html` — minimal landing page (logo, one-liner, legal links). Added
  in C8 so visitors no longer see this README as the homepage.
- `terms/` + `privacy/` — legal pages (the URLs both apps' `LegalLinks.swift`
  point at); grounded in the app repo's `docs/privacy-evidence.md` +
  `docs/terms-evidence.md`, operator/contact/jurisdiction confirmed by the
  owner 2026-08-26. Re-review both when C9 (scan photo storage), payments,
  or AI features ship.
- `confirm/` — client-invite email confirmation landing page. The invitation
  email (Supabase edge function `send-client-invite` in the main repo) links
  here with `?token=…`; the page validates the token against the
  `confirm-client-email` edge function (JSON API) and performs the
  confirmation on an explicit button tap, so email link-scanners can never
  consume the token.

Pages must be hosted OFF `*.supabase.co` — the Supabase gateway flattens all
HTML responses (functions and storage alike) to `text/plain` with a sandbox
CSP as an anti-phishing measure.


