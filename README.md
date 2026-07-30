# finanzuebersicht-site

Öffentliche Legal-/Support-Seiten für **Finanzübersicht** (App Store Connect) —
analog zu [simpletd-site](https://github.com/Thomas-Menzl-Softwareentwicklung/simpletd-site)
bzw. [simpletd.thomasmenzl.de](https://simpletd.thomasmenzl.de) (DE/EN-Umschaltung, Umsatzsteuerhinweis).

| Seite | URL (DE) | URL (EN) | ASC-Feld |
|-------|----------|----------|----------|
| Support | `https://finanzuebersicht.thomasmenzl.de/` | `…/en/` | Support URL |
| Privacy | `https://finanzuebersicht.thomasmenzl.de/privacy.html` | `…/en/privacy.html` | Privacy Policy URL |
| Impressum | `https://finanzuebersicht.thomasmenzl.de/impressum.html` | `…/en/impressum.html` | DE-Pflicht |

Fallback ohne Custom Domain:

`https://thomas-menzl-softwareentwicklung.github.io/finanzuebersicht-site/`

## Setup

1. GitHub Pages (Repo → Settings → Pages):
   - Source: **Deploy from a branch**
   - Branch: `main`
   - Folder: **`/`** (Repo-Root)

```bash
gh api repos/Thomas-Menzl-Softwareentwicklung/finanzuebersicht-site/pages \
  -X POST \
  -f build_type=legacy \
  -f source[branch]=main \
  -f source[path]=/
```

2. Custom Domain (wie SimpleTD):
   - DNS CNAME: `finanzuebersicht.thomasmenzl.de` → `thomas-menzl-softwareentwicklung.github.io`
   - In Pages Custom Domain eintragen + HTTPS erzwingen
   - `CNAME` im Repo enthält bereits `finanzuebersicht.thomasmenzl.de`

3. Optional als Submodule im App-Repo:

```bash
cd /Users/thomas/dev/finanzuebersicht/finanzuebersicht-1
git submodule add https://github.com/Thomas-Menzl-Softwareentwicklung/finanzuebersicht-site.git website
```

Site-Änderungen: in **diesem** Repo committen + pushen (nicht im App-Repo).
