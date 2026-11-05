# MuuuhFa 2027 – App veröffentlichen (kostenlos)

Alles hier ist kostenlos: **GitHub Pages** (Hosting) und **OneSignal** (Push, Gratis-Tarif).
Dauer: ca. 45 Minuten. Du brauchst nur Browser und E-Mail.

## Schritt 1 – Inhalte anpassen (`data.json`)
Öffne `data.json` mit einem Texteditor und ersetze:
- Programm: die Einträge mit "BEISPIEL" durch das echte Programm
- Sponsoren: Name, Kurztext, `url` (Website) und optional `logo` (z. B. `sponsor1.png`, Datei in denselben Ordner legen)
Achtung: Anführungszeichen und Kommas nicht löschen. Prüfen kannst du es auf https://jsonlint.com

## Schritt 2 – GitHub-Konto und Repository
1. Konto anlegen auf https://github.com (kostenlos).
2. Oben rechts **+ → New repository**. Name: `muuuhfa`. **Public**. Create repository.
3. **uploading an existing file** anklicken, ALLE Dateien aus dem Ordner `muuuhfa-app` hineinziehen (nicht den Ordner selbst, sondern die Dateien), **Commit changes**.

## Schritt 3 – Veröffentlichen mit GitHub Pages
1. Im Repository: **Settings → Pages**.
2. Source: **Deploy from a branch**, Branch **main**, Ordner **/ (root)** → Save.
3. Nach 1–2 Minuten steht oben die Adresse, z. B. `https://DEINNAME.github.io/muuuhfa/`
4. Adresse auf dem Handy öffnen und testen.

## Schritt 4 – Push-Benachrichtigungen (OneSignal)
1. Konto auf https://onesignal.com anlegen (Free).
2. **New App/Website** → Name `MuuuhFa` → Plattform **Web**.
3. Konfiguration: **Custom Code**.
   - Site Name: MuuuhFa
   - Site URL: deine komplette GitHub-Pages-Adresse, z. B. `https://DEINNAME.github.io/muuuhfa/`
   - Auto Resubscribe: an
   - **Service Worker**: Pfad `sw.js` angeben (nicht den Standard-Dateinamen). Hinweis: "Advanced Push Settings", Pfad `sw.js`, Scope `/muuuhfa/`.
4. Speichern. Die **App ID** kopieren (Format `xxxxxxxx-xxxx-…`).
5. In `index.html` die Zeile
   `const ONESIGNAL_APP_ID = "HIER-ONESIGNAL-APP-ID";`
   ersetzen durch deine App ID. Datei auf GitHub neu hochladen (Add file → Upload files, gleiche Datei überschreibt).
6. Test: App öffnen → "Benachrichtigungen aktivieren" → erlauben. In OneSignal **Messages → New Push** senden.

**iPhone-Hinweis:** Push geht nur ab iOS 16.4 und nur, wenn die App zuvor über **Teilen → Zum Home-Bildschirm** installiert wurde. Die App zeigt diesen Hinweis selbst.

## Schritt 5 – News und Programmänderungen
- News: in `data.json` unter `"news"` einen Eintrag ergänzen (neueste werden oben angezeigt), auf GitHub die Datei bearbeiten (Stift-Symbol) → Commit.
- Danach in OneSignal eine Push-Nachricht senden.
- Die App lädt neue Inhalte beim nächsten Öffnen automatisch.

## Schritt 6 – Verbreiten
- Adresse als QR-Code erzeugen (z. B. https://qrcode-monkey.com) und auf Plakat/Flyer drucken.
- Eigene Adresse später möglich (Domain ca. 10 €/Jahr), nicht nötig.

## Kosten
GitHub Pages: 0 €. OneSignal Free: 0 € (für 100–500 Besucher ausreichend). Domain: optional.
