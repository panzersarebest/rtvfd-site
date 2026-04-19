# Richland Township Fire &amp; EMS Website

A static single-page website for Richland Township Volunteer Fire Department in Glenmont, Ohio. Plain HTML and CSS. No WordPress, no Elementor, no monthly fee, no credit card required to keep it alive.

## Files

```
rtvfd-site/
├── index.html
├── styles.css
├── README.md
└── images/
    ├── logo-main.jpeg              Maltese cross patch ("The Desire to Serve")
    ├── logo-special-ops.jpeg       Rescue 503 Technical Rescue Team patch
    ├── hero-tanker-502.jpg         Tanker 502 hero background
    ├── ambulance.jpg               EMS 52 ambulance (About section + Apparatus)
    ├── apparatus-engine-501.jpg
    ├── apparatus-tanker-502.jpg
    ├── apparatus-rescue-503.jpg
    ├── apparatus-brush-505.jpg
    ├── apparatus-atv.jpg
    └── team-*.jpg                  12 team portraits
```

## Preview it

Double-click `index.html`. Or for a proper local server:

```bash
cd rtvfd-site
python3 -m http.server 8000
# open http://localhost:8000
```

## What still needs to be filled in

Open `index.html` and search for `[First Name]`, `[Name]`, or `[rank/cert]` — three team members need their details:

1. **J. Schlabach** (nametag visible, looks related to Katie)
2. **J. Troyer** (nametag visible)
3. **The unidentified woman** in `team-unknown-1.jpg` — need her name and certifications

Easy edit: find the `<article class="person">` blocks at the bottom of the Team section and replace the placeholder text.

**Silhouette note:** You mentioned you turned a couple of photos into silhouettes for members you couldn't photograph. If any of those are what I'm seeing here, let me know which ones and we can style those cards differently (silhouette + "Photo Coming Soon" caption instead of a name).

**Engine 501:** I labeled the pumper as "Engine 501" because the door reads "50_" with the last digit partially obscured. If it's actually 504 or something else, edit `index.html` in the Apparatus section.

## Deploying for free

You own `richlandtwpfire.com` at GoDaddy. Here's the best path:

### Option A — Cloudflare Pages (recommended, zero cost, never expires)

1. **Make a GitHub account** if you don't have one (github.com, free).
2. **Create a new repo** named `rtvfd-site`. Set it public. Upload this entire folder (drag &amp; drop works).
3. **Sign up for Cloudflare** (cloudflare.com, free). Go to pages.cloudflare.com.
4. Click **Create a project** → **Connect to Git** → authorize GitHub → pick `rtvfd-site`.
5. **Build settings:** leave everything blank. Framework preset = "None". Build output directory = blank. Click Save and Deploy.
6. **30 seconds later** you have a working site at something like `rtvfd-site.pages.dev`.
7. In Cloudflare Pages → your project → **Custom domains** → add `richlandtwpfire.com` and `www.richlandtwpfire.com`.
8. Cloudflare will tell you to update nameservers at GoDaddy. Log into GoDaddy → DNS settings → change nameservers to the two Cloudflare provides. Save.
9. Wait 10-30 minutes for DNS to propagate. Done. Forever free.

Any edit you push to GitHub automatically redeploys in ~30 seconds. No credit card on file. No plugin updates. Nothing to expire.

### Option B — Netlify (same idea, also free)

Same GitHub repo, go to netlify.com instead, "Add new site" → "Import from GitHub" → pick repo → deploy. Custom domain works the same way.

## Editing the site later

Three easy options:

1. **GitHub web interface:** click the file, click the pencil icon, edit, commit. Redeploys automatically.
2. **Claude Code:** clone the repo to your computer, point Claude Code at it, describe what you want ("add a news post titled X", "swap this photo", "update the chief's name"), and it edits and pushes.
3. **Edit locally:** clone the repo, edit the files in VS Code, push with Git.

## Design reference

- Palette: navy `#0D2B4E`, fire red `#C41E3A`, ivory paper `#FAF7F1`, gold accent `#C8A24B`. All defined as CSS variables at the top of `styles.css` — change once, applies site-wide.
- Fonts: Fraunces (display) + Inter Tight (body), both free from Google Fonts.
- Mobile-first responsive — slide-down nav on phones, grids collapse gracefully.
- No tracking, no cookies, no analytics (add if you want, but not installed by default).

## What's on the site

- Header with your real phone, address, email (rtfd527@gmail.com), Facebook link
- Hero with Tanker 502 photo, Maltese cross badge, and "The Desire to Serve" motto
- About section with original mission text and ambulance photo
- Special Operations callout with Rescue 503 patch and the technical rescue capabilities
- Team section with 12 member cards (3 need first names + ranks)
- Apparatus section: Engine 501, Tanker 502, Rescue 503, Brush 505, EMS 52, and the Polaris ATV
- Contact section with Google Map and all contact info
- Footer

Questions? Come back to Claude and we'll iterate.
