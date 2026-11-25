# piercegorman.com

A one-page static site: plain HTML and CSS with no build step, hosted on **GitHub Pages** from `github.com/pierce-gorman2/pg.com`. Every push to `main` goes live within a minute or two.

## Files
| File | Purpose |
|---|---|
| `index.html` | The page, including all SEO tags and the JSON-LD (ProfilePage, Person, PodcastSeries) |
| `pierce.jpg` | Bio photo on the page and the image in Google's structured data |
| `og-image.jpg` | Wide crop used when the link is shared (texts, LinkedIn, etc.) |
| `favicon.svg`, `favicon.png`, `apple-touch-icon.png` | "PG" monogram icons |
| `robots.txt`, `sitemap.xml` | Crawl rules and the sitemap |
| `CNAME` | Tells GitHub Pages the site's domain is piercegorman.com |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is |
| `_headers` | Only used if the site ever moves to Cloudflare Pages or Netlify; GitHub Pages ignores it |

## Turn on GitHub Pages (one time)
1. Go to github.com/pierce-gorman2/pg.com → **Settings** → **Pages** (left sidebar).
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**, **Branch** to **main**, and the folder to **/ (root)**. Click **Save**.
3. **Custom domain** should already show `piercegorman.com`. If it doesn't, type it in and save.

## Point piercegorman.com at it (Squarespace Domains)
1. Log in to Squarespace → **Domains** → **piercegorman.com** → **DNS** → **DNS Settings**.
2. Delete the **Squarespace Defaults** record group, since it points the domain at the "Coming Soon" page.
3. Add these records under **Custom records**:

| Host | Type | Data |
|---|---|---|
| @ | A | 185.199.108.153 |
| @ | A | 185.199.109.153 |
| @ | A | 185.199.110.153 |
| @ | A | 185.199.111.153 |
| www | CNAME | pierce-gorman2.github.io |

4. Wait 15–60 minutes. Then, back in GitHub → Settings → Pages, tick **Enforce HTTPS** once it lets you (it can take up to a day for the certificate).

## After it's live (for ranking and a knowledge panel)
1. **Google Search Console**: add `piercegorman.com` as a Domain property (verify with the DNS TXT record it gives you, added in Squarespace DNS), submit `https://piercegorman.com/sitemap.xml`, and use **URL Inspection → Request indexing**.
2. Test with the [Rich Results Test](https://search.google.com/test/rich-results) and [Schema validator](https://validator.schema.org/).
3. **Link back from every profile.** Put `https://piercegorman.com` in the website or bio field on LinkedIn, YouTube, Instagram, the podcast pages, and Traditio.
4. Use the same name, headshot, and one-line description everywhere.
