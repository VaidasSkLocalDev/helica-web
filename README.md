# helica-web

Static pages for Helica, served via GitHub Pages.

- `confirm/` — client-invite email confirmation landing page. The invitation
  email (Supabase edge function `send-client-invite` in the main repo) links
  here with `?token=…`; the page validates the token against the
  `confirm-client-email` edge function (JSON API) and performs the
  confirmation on an explicit button tap, so email link-scanners can never
  consume the token.

Pages must be hosted OFF `*.supabase.co` — the Supabase gateway flattens all
HTML responses (functions and storage alike) to `text/plain` with a sandbox
CSP as an anti-phishing measure.

Planned (C8): legal pages (terms, privacy) at helica.lt/terms + /privacy.
