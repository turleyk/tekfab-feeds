# tekfab-feeds

Public files for TekFab's Google Merchant Center feed, served by GitHub Pages at
https://feeds.tekfab.co.uk/

| Path | What it is |
|------|------------|
| `googleMerchant.xml` | The Google Merchant Center product feed. Built automatically from the private repo `tekfab-product-data` (workflow "Merchant Center feed") whenever product data, feed rules or product images change. **Do not edit here.** |
| `images/hero/<configuration>.jpg` | Google main image for each lantern configuration: its bar-layout render floating above a real install. Made by `scripts/hero/hero.py` in `tekfab-product-data`. |
| `images/render/<configuration>.jpg` | Plain style render for each configuration (first additional image in the feed). |
| `images/lifestyle-*.jpg` | Lifestyle photo per lantern type. |
| `images/thermlock.jpg`, `interior-s1-lantern.jpg`, `sheervent-close-up.jpg` | Extra images in the feed. |
| `images/upstand-diagram-s1-lantern.jpg`, `upstand-base-diagram-s1-lantern.jpg` | Upstand diagrams. Used in the feed **and shown on every lantern's product page** (Product Details). Do not rename or remove. |
| `CNAME`, `robots.txt` | Custom domain and permission for crawlers to fetch the files. |

A *configuration* is the SKU without its size, e.g. `2WAY-ALR-V0-R4-J0-P8`.

## Changing things
- **The feed:** change the product data or `config/merchant_feed.yaml` in `tekfab-product-data`. It republishes here by itself.
- **An image:** replace the file here with the same name and commit. Google picks it up on its next fetch. Keep images at least 500 x 500 px (1500 px or more is better).
- **A new image:** add it under `images/`, then reference it in `config/merchant_feed.yaml`.

Only public product information belongs here. This repo is kept apart from the shop's scripts so the
token that updates it cannot change the shop.
