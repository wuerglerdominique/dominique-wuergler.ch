# dominique-wuergler.ch

Statische Portfolio-Seite. Kein Build-Schritt, kein JavaScript, keine externen Fonts, keine Analytics.

## Lokal testen

```
python3 -m http.server 8000
```

Dann `http://localhost:8000` öffnen. Fensterbreite auf Handygrösse ziehen und den dunklen Systemmodus testen (`prefers-color-scheme`).

## Quelle der Texte

Alle Inhalte stammen aus `../inhalt.md` im übergeordneten Ordner (nicht Teil dieses Repos). Änderungen zuerst dort, dann hier ins HTML übertragen.

## Deployment (siehe `../plan.md`, Schritt 4 und 5)

1. Inhalt dieses Ordners (`site/`) in ein neues **öffentliches** GitHub-Repo `dominique-wuergler.ch` pushen. Nicht das Vault-Repo verwenden.
2. In den Repo-Einstellungen: Pages auf Branch `main`, Ordner `/` stellen.
3. Custom Domain `dominique-wuergler.ch` eintragen (liest die `CNAME`-Datei), "Enforce HTTPS" aktivieren, sobald das Zertifikat ausgestellt ist.
4. Bei Infomaniak im DNS-Manager für `dominique-wuergler.ch`:
   - vier A-Records auf `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (vor dem Eintragen gegen die aktuelle GitHub-Pages-Doku verifizieren)
   - ein CNAME auf `www` nach `wuerglerdominique.github.io`
5. Nach Propagation: `dig dominique-wuergler.ch`, dann `curl -I https://dominique-wuergler.ch` prüfen (200, HTTPS).

## Verifikation vor jedem Deploy

- Alle Zahlen auf der Seite gegen `../../bewerbung/zahlen_baselines.md` gegenlesen.
- Anonymitäts-Check: kein Firmen-, Kunden- oder Personenname.
- `grep -rn -- '--\|—' .` — keine Gedankenstriche, kein "--" als Satzzeichen.
