# piercegorman.com

A one-page static site: plain HTML and CSS with no build step, hosted on Cloudflare Pages.

## Files
| File | Purpose |
|---|---|
| `index.html` | The page, including all SEO tags and the JSON-LD (ProfilePage → Person) |
| `pierce.jpg` | **You add this.** Headshot used on the page and in social previews |
| `favicon.svg`, `favicon.png`, `apple-touch-icon.png` | "PG" monogram icons |
| `robots.txt`, `sitemap.xml` | Crawl rules and the sitemap |
| `_headers` | Cloudflare Pages security and cache headers |

## Deploy (Cloudflare Pages + GitHub)

1. **Create the GitHub repo.** On github.com, click New repository, name it `piercegorman.com`, and leave it empty.
2. **Push this folder** (run these in this folder):
   ```bash
   git add -A
   git commit -m "Initial site"
   git remote add origin https://github.com/YOUR-USERNAME/piercegorman.com.git
   git push -u origin main
   ```
3. **Create the Pages project.** In the Cloudflare dashboard, go to **Workers & Pages → Create → Pages → Connect to Git**, pick the repo, and use these settings:
   - Framework preset: **None**
   - Build command: *(leave blank)*
   - Build output directory: `/`
   Click **Save and Deploy**. You'll get a `*.pages.dev` URL. Check the site there first.

## Point piercegorman.com at it

**Easiest: move the domain's DNS to Cloudflare** (this is free, and the domain can stay with your current registrar):
1. Cloudflare dashboard → **Add a domain** → enter `piercegorman.com` → Free plan.
2. Cloudflare shows two nameservers. At your registrar (GoDaddy, Namecheap, Squarespace, etc.), replace the domain's nameservers with those two. Changes usually take minutes, but can take up to 24h.
3. Back in **Workers & Pages → your project → Custom domains → Set up a custom domain**, add `piercegorman.com`. Cloudflare creates the DNS record for you.
4. Add `www.piercegorman.com` the same way. Then add a redirect so `www` points to the bare domain: **Rules → Redirect Rules → Create rule → template "Redirect from WWW to root"**. This prevents duplicate-URL SEO issues.

**If you'd rather keep DNS at your registrar:** add a `CNAME` record with name `www` pointing to `your-project.pages.dev`. Note that the bare `piercegorman.com` only works if your registrar supports CNAME flattening or ALIAS records. If it doesn't, use the nameserver method above.

## After it's live (for ranking and a knowledge panel)
1. **Google Search Console**: add `piercegorman.com` as a Domain property (verify with a DNS TXT record in Cloudflare), submit `https://piercegorman.com/sitemap.xml`, and use **URL Inspection → Request indexing**.
2. Test with the [Rich Results Test](https://search.google.com/test/rich-results) and [Schema validator](https://validator.schema.org/).
3. **Link back from every profile.** Put `https://piercegorman.com` in the website or bio field on LinkedIn, YouTube, Instagram, X, the podcast page, and Traditio. Two-way links between this page and those profiles are the strongest signal that they all describe the same Pierce Gorman.
4. Use the same name, headshot, and one-line description everywhere.
