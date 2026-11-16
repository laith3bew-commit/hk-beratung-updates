# HK Beratung – Updates

Update-Server der Beratungs-App des Ambulanten Pflegedienstes Heike Kühn.

Dieses Repository enthält **nur** die fertigen App-Dateien (APK) und `version.json`.
Es enthält **keine Patientendaten**, keinen Quellcode und keinen Signaturschlüssel.

- `version.json` – aktuelle Version, Link zur APK, SHA-256-Prüfsumme, Neuerungen
- `apk/` – die fertigen App-Dateien

## So funktioniert es
1. Die App liest beim Anmelden `version.json` aus diesem Repository (Zweig `main`).
2. Ist `versionCode` höher als die installierte Version, erscheint „Update verfügbar“.
3. Die App lädt die APK, prüft SHA-256, Paketname, Version und Signaturschlüssel und öffnet den Android-Installer.
4. Die Mitarbeiterin tippt „Installieren“ – alle Daten bleiben erhalten.

## Neues Update veröffentlichen
Im Quellcode: `tools/release.sh <versionName> <versionCode> "Neu 1" "Neu 2"`
(Pflicht-Update: `PFLICHT=1 tools/release.sh …`)

Regeln: immer derselbe Signaturschlüssel · `versionCode` immer höher · Repository bleibt öffentlich, damit die App ohne Passwort lesen kann.
