# EP Planner PRO — Clean Repo

**Wat is dit?** Een opgeschoonde, deploy-klare broncode van jouw app (React + Vite + Tailwind), geoptimaliseerd voor Netlify (incl. functions).

## Belangrijkste fixes
- **Streams:** 7 artiesten toegevoegd + cache-buster & `no-store` → lijst pakt altijd de nieuwste `artists.json`.
- **Fallback:** `public/streams-append.js` injecteert de 7 artiesten ook runtime (extra vangnet).
- **Releases:** cloud-sync polling elke 5s via `/.netlify/functions/kv-store` → iedereen ziet groen/rood realtime.
- **Netlify headers:** `public/_headers` met `no-store` voor `artists.json` en `streams.js`.
- **Opschoning:** verdubbelde mappen en build-output verwijderd.

## Mappen
- `src/` — React broncode
- `public/` — statische assets (`streams.html/js/css`, `artists.json`, `_headers`, `_redirects`)
- `netlify/functions/` — serverless functies (kv-store, getData/setData/appendStreams)

## Deploy (GitHub → Netlify)
1. Nieuwe repo aanmaken op GitHub en **deze map uploaden** (inhoud van `EPPLANNERPRO-clean/`).
2. Netlify → **New site from Git** → koppel repo.
3. Build command: `npm run build` — Publish directory: `dist`.
4. Klaar.
