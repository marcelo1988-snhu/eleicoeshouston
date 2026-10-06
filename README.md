# Eleições Houston — browser deployment

This package is already compiled. No build or installation on your computer is needed.

1. Create a private GitHub repository named `eleicoeshouston`.
2. Extract this ZIP. Upload the contents of the extracted folder to the repository root using GitHub's **Add file → Upload files**. Upload `server/`, `public/`, `wrangler.json`, `package.json` and the documentation; do not upload the ZIP itself. The two JSON files must appear at the repository root.
3. Open your existing Cloudflare Worker `eleicoeshouston` → **Settings → Build** and connect this repository.
4. Use branch `main`, leave the build command empty, set deploy command to `npm run deploy`, and root directory to `/` (or its default repository root).
5. Allow Cloudflare to create its deployment token. Keep deployment credentials in Cloudflare, not in this repository.
6. Save and deploy. Test `https://eleicoeshouston.admin-houston.workers.dev` with sections 0131 and 3667 (both A1).

Only app code and public maps/logos belong in this repository. The private voter list and lookup secret must stay outside GitHub. Title lookup remains disabled pending private database configuration, import and validation.

Cloudflare will install the pinned Wrangler tool in its own build environment. The package has no local build step and deploys to the existing Worker name in `wrangler.json`.

The first deployment includes section lookup, map, priority selector and arrival information. It does not create or populate D1 or configure a lookup secret. Those and the custom domain are the next steps.

Hosted on Cloudflare Workers.
