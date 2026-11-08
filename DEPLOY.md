# Publishing usesteady.health

The site is plain static files (no build step). Preview locally:

    python -m http.server 8800     # then open http://localhost:8800

## 1. Host it (GitHub Pages, free)

1. Create a repo (for example `Arshyi/steady-site`) and push this folder to `main`.
2. Repo Settings > Pages > Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Custom domain: `usesteady.health` (the `CNAME` file here already says so).

## 2. Point the domain at it (Porkbun > Domain Management > DNS)

The domain is registered at Porkbun, not GoDaddy. Delete any default "parked" ALIAS/A/CNAME
records for the root and www, then add:

| Type  | Host | Answer                |
| ----- | ---- | --------------------- |
| A     | (blank, the root) | 185.199.108.153 |
| A     | (blank) | 185.199.109.153 |
| A     | (blank) | 185.199.110.153 |
| A     | (blank) | 185.199.111.153 |
| CNAME | www  | <github-username>.github.io |

DNS can take minutes to hours (up to 24 h). When GitHub shows the DNS check as passed, tick
"Enforce HTTPS" in Pages settings.

## Before presenting

Open https://usesteady.health on your phone, on mobile data, a few hours ahead.
