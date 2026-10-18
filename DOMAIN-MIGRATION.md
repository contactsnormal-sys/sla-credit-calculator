# Plan: move to sla.2jagency.com (NOT applied)

Status 2026-10-18: prepared only. No CNAME file in the repo yet (adding it before DNS exists would redirect the live site to a domain that does not resolve).

Order (after Orion's approval):
1. Cloudflare, account "Operateur15@pm.me's Account", zone 2jagency.com: add record `CNAME  sla  contactsnormal-sys.github.io`, proxy status **DNS only** (grey cloud), TTL Auto.
2. Check: `dig +short sla.2jagency.com CNAME` returns `contactsnormal-sys.github.io.`
3. Repo: add file `CNAME` containing exactly `sla.2jagency.com`, commit, push (or GitHub > Settings > Pages > Custom domain = sla.2jagency.com, which creates the same file).
4. Wait for GitHub's DNS check and certificate, then tick **Enforce HTTPS**.
5. Update canonical URLs, sitemap.xml, JSON-LD url, robots.txt Sitemap line to https://sla.2jagency.com/ ; add the new property in Search Console.
6. Old github.io URLs redirect automatically to the custom domain.
Optional hardening: verify the domain 2jagency.com for the GitHub account (Settings > Pages > Verified domains, TXT `_github-pages-challenge-contactsnormal-sys`), value given by GitHub.
