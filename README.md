# R.E. Cost Seg Support

Static Astro site for `support.recostseg.com`.

The complete sign-in help page is served directly from `/`.

## Local development

```bash
npm install
npm run dev
```

## Migration phases

The sign-in page automatically builds as Phase A before August 31, 2026 at
12:00 a.m. Central Time and as Phase B afterward. Because the site is static,
redeploy it on or after August 31 to publish Phase B.

To force a phase during a build:

```bash
PUBLIC_MIGRATION_PHASE=A npm run build
PUBLIC_MIGRATION_PHASE=B npm run build
```

## Production build

```bash
npm run check
npm run build
```

## Cloudflare deployment

Authenticate Wrangler with the Cloudflare account that owns `recostseg.com`,
then run:

```bash
npm run deploy
```

After the first deployment, add `support.recostseg.com` under the Worker's
custom domains. Cloudflare creates the DNS record and TLS certificate.
