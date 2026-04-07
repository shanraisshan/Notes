# CDN (Content Delivery Network)
A geographically distributed network of servers that delivers web content to users from the server **closest to them**, reducing latency and improving load times.

## ELI5 (Explain Like I'm 5)

CDN Term|Pizza Kitchen Analogy
-|-
**Origin Server**|The main pizza shop in New York where all recipes are created
**Edge Servers**|Mini kitchens opened in every major city with the same recipes ready to go
**CDN**|The whole network of mini kitchens, so whoever orders gets pizza from the **nearest kitchen** instead of waiting for delivery from New York

## How it works

1. Your origin server (e.g., in New York) holds the original content
2. CDN copies that content to **edge servers** worldwide (Tokyo, London, Sydney, etc.)
3. When a user in Tokyo requests your site, they get served from the Tokyo edge server instead of New York

## Key benefits

- **Faster load times** — content served from nearby servers
- **Reduced origin server load** — CDN handles most requests
- **DDoS protection** — distributed infrastructure absorbs attacks
- **High availability** — if one server fails, another takes over

## Real-world CDN providers

Provider|Notable users
-|-
**Cloudflare**|Discord, Shopify, ~20% of all websites
**AWS CloudFront**|Netflix, Slack, Twitch
**Akamai**|Apple, Microsoft, major banks
**Fastly**|GitHub, Stripe, The New York Times
**Google Cloud CDN**|Spotify, PayPal

## Do you get CDN by default?

No. Deploying to a single server (e.g., in UAE) does **not** give you a CDN. You must set it up separately.

### Without a CDN
- User in **UAE** → fast (nearby server)
- User in **USA** → slow (~200-300ms latency per request)
- User in **Japan** → slow
- User in **Brazil** → very slow

### CDN depends on your hosting choice

Hosting|CDN situation
-|-
**Traditional VPS** (DigitalOcean, AWS EC2)|No CDN. Add one manually (Cloudflare, CloudFront, etc.)
**Vercel / Netlify**|CDN included automatically for static assets
**AWS S3 + CloudFront**|CDN if you configure CloudFront
**Shopify / Wix**|CDN built-in, handled for you

## Simplest way to add a CDN

**Cloudflare** (free tier available):
1. Point your domain's DNS to Cloudflare
2. Cloudflare sits between users and your server
3. It caches static content (images, CSS, JS) on edge servers worldwide
4. Users get served from the nearest Cloudflare edge

## What gets cached vs what doesn't

Cached on CDN|NOT cached
-|-
Images, CSS, JS, fonts, videos (static assets)|API calls, cart updates, checkout, login (dynamic content that changes per user)
