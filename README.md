# finanzuebersicht-site

Öffentliche Legal-/Support-Seiten für **Finanzübersicht** (App Store Connect) —
analog zu [simpletd-site](https://github.com/Thomas-Menzl-Softwareentwicklung/simpletd-site).

| Seite | URL | ASC-Feld |
|-------|-----|----------|
| Support | `https://finanzuebersicht.thomasmenzl.de/` | Support URL |
| Privacy | `https://finanzuebersicht.thomasmenzl.de/privacy.html` | Privacy Policy URL |
| Impressum | `https://finanzuebersicht.thomasmenzl.de/impressum.html` | DE-Pflicht |

Fallback ohne Custom Domain:

`https://thomas-menzl-softwareentwicklung.github.io/finanzuebersicht-site/`

## Setup

1. USt-Platzhalter ersetzen: `REPLACE_WITH_VAT_OR_EXEMPTION` in `impressum.html` (E-Mail/Adresse sind gesetzt).
2. GitHub Pages (Repo → Settings → Pages):
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

3. Custom Domain (wie SimpleTD):
   - DNS CNAME: `finanzuebersicht.thomasmenzl.de` → `thomas-menzl-softwareentwicklung.github.io`
   - In Pages Custom Domain eintragen + HTTPS erzwingen
   - `CNAME` im Repo enthält bereits `finanzuebersicht.thomasmenzl.de`

4. Optional als Submodule im App-Repo:

```bash
cd /Users/thomas/dev/finanzuebersicht/finanzuebersicht-1
git submodule add https://github.com/Thomas-Menzl-Softwareentwicklung/finanzuebersicht-site.git website
```

Site-Änderungen: in **diesem** Repo committen + pushen (nicht im App-Repo).
