BUILDWISE WEBSITE: DEPLOYMENT GUIDE
====================================

This is a static website. It needs no server code and no database.

FOLDER CONTENTS
  index.html     The whole site (all pages, styles, scripts, product data)
  thumbs.json    Thumbnail images for listing pages
  packs/*.json   Full-size product photos, one file per product family
  hero-*.jpg     Home page slideshow images

HOW TO DEPLOY (any one of these)
  Netlify:          drag the unzipped folder onto app.netlify.com/drop, then add the custom domain
  Vercel:           new project, upload the folder, framework preset "Other"
  Cloudflare Pages: Create project, choose Direct Upload, upload the folder
  cPanel / any host: upload everything to public_html (keep the folder structure)

Then point the domain's DNS to the host, as the host's instructions describe.

NOTES
- Upload the folder exactly as it is. index.html loads thumbs.json and packs/ by relative path.
- Opening index.html straight from disk (file://) will NOT load the photos.
  Preview it through a web server or on the host.
- Navigation uses URL hashes (#products, #p-pivot, #contact), so no rewrite rules are needed.
- Fonts load from Google Fonts (Jost).
- The contact form opens a pre-filled email to ran9155@gmail.com.
  To send submissions to a CRM or form service (Formspree, Netlify Forms, Zoho), replace the
  form "submit" handler near the end of index.html.
- Enable HTTPS on the host (free on all the hosts above).

BEFORE GOING LIVE
- Privacy Policy and Terms pages are placeholders; add the legal text.
- Product photos come from supplier catalogs; confirm usage rights or replace them.
