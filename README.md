# GTM Test Pages

Banco di prova per GTM + Meta Pixel + CAPI.

## File

- `index.html` — Landing page con form e bottone CTA
- `thank-you.html` — Thank You page (simula conversione Lead)

## GTM Container

**Web Container ID:** `GTM-W3FN9J3S`

## Come pubblicare su GitHub Pages

1. Crea un nuovo repository su GitHub (es. `gtm-test`)
2. Carica entrambi i file (`index.html` e `thank-you.html`)
3. Vai su **Settings → Pages**
4. Source: **Deploy from branch → main → / (root)**
5. Salva — GitHub Pages pubblica in ~1 minuto

L'URL sarà: `https://tuousername.github.io/gtm-test/`

## Eventi tracciati

| Evento | Trigger | Pagina |
|---|---|---|
| `page_view` | Caricamento pagina | entrambe |
| `generate_lead` | Click "Invia form" | index.html |
| `cta_click` | Click "Clicca CTA" | index.html |
| `lead` | Caricamento TY page | thank-you.html |

## Event ID e deduplication

L'`event_id` viene generato sulla landing al momento del submit e passato alla Thank You page via query string (`?event_id=...`). Questo permette la deduplication tra Pixel client-side e CAPI server-side.

## Come testare con GTM Preview

1. Vai su tagmanager.google.com
2. Apri il container Web → **Anteprima**
3. Inserisci l'URL GitHub Pages
4. Verifica che gli eventi appaiano nel pannello GTM
