# Quick Site — vortex-cx.com

Static landing site for Google OAuth verification and product presence.

## Pages
- `index.html` — Landing page (product overview, features, CTA)
- `privacy.html` — Privacy Policy (GDPR/CCPA/LGPD compliant)
- `terms.html` — Terms of Service

## Stack
- Static HTML + Tailwind CSS (CDN)
- No build step, no framework, no runtime
- Shared styles in `css/site.css`

## Hosting
Intended for Caddy on the dev VPS. Caddy config:

```
vortex-cx.com {
    root * /var/www/vortex-cx
    file_server
}
```

Caddy auto-provisions Let's Encrypt SSL.

## Deployment
1. Point `vortex-cx.com` DNS A record to VPS IP
2. Copy files to `/var/www/vortex-cx/` on the server
3. Add Caddy site block and reload (`caddy reload`)
4. Verify HTTPS at `https://vortex-cx.com`

## Purpose
Required for Google OAuth consent screen verification (sensitive scopes: gmail.send, gmail.readonly). Google reviews:
- Homepage exists at the authorized domain
- Privacy policy URL is accessible
- Terms of service URL is accessible
- Domain is verified in Google Search Console
