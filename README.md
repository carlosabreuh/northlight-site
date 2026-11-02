# Northlight Aerial — site launch steps

Static site: `index.html` + `CNAME`. No build step.

## 1. Create the mailbox (GoDaddy, ~5 min)
1. GoDaddy → My Products → **Microsoft 365 Email Essentials** → Set up.
2. Choose the domain `northlightaerial.com`, create user **hello@northlightaerial.com**, set a password.
3. GoDaddy adds the MX / SPF / autodiscover DNS records for you. Wait up to an hour, then sign in at outlook.office.com.
4. Optional: forward to your personal inbox (Outlook → Settings → Mail → Forwarding) so you see leads immediately.

## 2. Wire the contact form (Web3Forms, free, ~2 min)
1. Go to https://web3forms.com → "Create your Access Key" → enter `hello@northlightaerial.com`.
2. Open the confirmation email in that mailbox and copy the key.
3. In `index.html`, replace `YOUR-WEB3FORMS-ACCESS-KEY` with it (one place).
Form submissions then arrive as emails in hello@. Free tier is 250/month.

## 3. Host it on GitHub Pages (free)
1. Create a new GitHub repo, e.g. `northlight-site`. Push `index.html` and `CNAME`.
2. Repo → Settings → Pages → Source: *Deploy from a branch* → `main` / root → Save.
3. Under "Custom domain" it will read `northlightaerial.com` from the CNAME file. Tick **Enforce HTTPS** once the cert issues (a few minutes).

## 4. DNS at GoDaddy
GoDaddy → DNS for northlightaerial.com → add:

| Type  | Name | Value |
|-------|------|-------|
| A     | @    | 185.199.108.153 |
| A     | @    | 185.199.109.153 |
| A     | @    | 185.199.110.153 |
| A     | @    | 185.199.111.153 |
| CNAME | www  | `<your-github-username>.github.io` |

Delete GoDaddy's default "Parked" A record. Leave the MX records alone (that's email).
Propagation: usually under an hour.

## 5. Before going public, make sure these are true
- Part 107 certificate in hand (the site says "FAA Part 107").
- Liability policy active (the site says "Insured").
- Replace the three "Recent work" placeholder frames with real stills.

## Later
- Hero video: export a 10–15 s, 1080p, ~5 MB H.264 loop; we'll add it with a poster frame and reduced-motion fallback.
- Google Business Profile → link to this site.
