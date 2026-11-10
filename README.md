# dominique-wuergler.ch

Statische Portfolio-Seite. Kein Build-Schritt, kein JavaScript, keine externen Fonts, keine Analytics.

Seiten: `index.html` (Portfolio) und `datenschutz.html` (Datenschutzerklärung, verlinkt in der Fusszeile; Google verlangt sie für die eigene OAuth-App "n8n Mail-Eingang" im Produktionsmodus).

## Lokal testen

```
python3 -m http.server 8000
```

Dann `http://localhost:8000` öffnen. Fensterbreite auf Handygrösse ziehen und den dunklen Systemmodus testen (`prefers-color-scheme`).

## Deployment

Gehostet über GitHub Pages, Custom Domain via `CNAME`-Datei. DNS zeigt bei Infomaniak auf die Standard-GitHub-Pages-Adressen.
