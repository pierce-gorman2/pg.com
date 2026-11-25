# piercegorman.com

A one-page static site: plain HTML and CSS with no build step, hosted on **Cloudflare Pages**, which deploys from `github.com/pierce-gorman2/pg.com`. Every push to `main` goes live within a minute or two. DNS for piercegorman.com is on Cloudflare (the domain is registered at Squarespace).

## Files
| File | Purpose |
|---|---|
| `index.html` | The page, including all SEO tags and the JSON-LD (ProfilePage, Person, PodcastSeries) |
| `pierce.jpg` | Bio photo on the page and the image in Google's structured data |
| `og-image.jpg` | Wide crop used when the link is shared (texts, LinkedIn, etc.) |
| `favicon.svg`, `favicon.png`, `apple-touch-icon.png` | "PG" monogram icons |
| `robots.txt`, `sitemap.xml` | Crawl rules and the sitemap |
| `_headers` | Cloudflare Pages security and cache headers |
| `CNAME`, `.nojekyll` | Only used if the site is ever hosted on GitHub Pages instead; Cloudflare ignores them |

## Hosting setup (already done)
- **Cloudflare Pages** project connected to the GitHub repo (framework: None, build command: blank, output directory: `/`).
- **Custom domains** on the Pages project: `piercegorman.com` and `www.piercegorman.com`.
- **Redirect rule** (Cloudflare → Rules → Redirect Rules): www → root, so there's only one address.
- Cloudflare DNS should have no leftover Squarespace records (`198.185.x.x`, `198.49.x.x`, `ext-sq.squarespace.com`).

## After it's live (for ranking and a knowledge panel)
1. **Google Search Console**: add `piercegorman.com` as a Domain property (verify with the DNS TXT record it gives you, added in Cloudflare DNS), submit `https://piercegorman.com/sitemap.xml`, and use **URL Inspection → Request indexing**.
2. Test with the [Rich Results Test](https://search.google.com/test/rich-results) and [Schema validator](https://validator.schema.org/).
3. **Link back from every profile.** Put `https://piercegorman.com` in the website or bio field on LinkedIn, YouTube, Instagram, the podcast pages, and Traditio.
4. Use the same name, headshot, and one-line description everywhere.
