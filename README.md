# Toby and the Reno Grass

Website for Toby and the Reno Grass, a bluegrass band from Reno, Nevada.

Plain static site, no build step. Hosted on GitHub Pages from the `main` branch root.

## Editing

The main page is `index.html`, the press kit is `epk.html`. Each section has a comment at the top explaining what to change:

- **Shows**: copy the commented `<li class="show">` example, one per gig. Move gigs to the "Past shows" list after they happen.
- **Music**: replace the placeholder tiles with YouTube `<iframe>` embeds.
- **Photos**: put images in `static/images/photos/` and swap the placeholder tiles for `<img>` tags.
- **Band**: one `.member` block per person; add photos under `static/images/band/`.
- **Hero photo**: add `static/images/hero.jpg` (wide, ~2000 px) and uncomment the `<img class="hero-photo">` line.
- **EPK**: `epk.html` holds the press kit (bios, press photos, video, stage plot, booking). Press photos and PDFs go in `static/epk/`.
- **Contact / booking**: search for `TODO` and the placeholder email `tobyandtherenograss@gmail.com`.

Styles are in `static/css/main.css`. Colors and fonts are variables at the top of that file.

When you change the CSS, bump the `?v=1` on the stylesheet link in `index.html` so browsers pick it up.

## Preview locally

```sh
cd tobyandtherenograss
python3 -m http.server 8000
# open http://localhost:8000
```

## Publishing

Push to `main`. GitHub Pages redeploys within a minute or two.

## Custom domain

Once the domain is registered:

1. Add a file named `CNAME` in the repo root containing just the domain, e.g. `tobyandtherenograss.com`, and push.
2. At the registrar, add DNS records:
   - `A` records for the apex (`@`) pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` record for `www` pointing to `lkraal.github.io`
3. In the repo on GitHub: Settings, Pages, confirm the custom domain and tick "Enforce HTTPS" once the certificate is issued (can take up to a day).
4. Set `og:url` in `index.html` to the final URL.
