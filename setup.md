# Lokale Einrichtung (Windows PowerShell)

## Backend

1. Installiere Node.js (npm wird mitgeliefert).
2. Öffne PowerShell im heruntergeladenen Projektverzeichnis.
3. Wechsle zu `backend` und führe aus:

```powershell
cd backend
Copy-Item db.example.json db.json
npm ci
$env:JWT_SECRET = "HIER_EIN_EIGENES_LANGES_ZUFAELLIGES_GEHEIMNIS_EINSETZEN"
npm start
```

Du solltest `Backend running at http://127.0.0.1:4000` sehen. Die `.env.example` wird nicht automatisch geladen; das Geheimnis muss als Umgebungsvariable gesetzt sein.

## Frontend

Öffne ein zweites Terminal **im Projekt-Hauptordner** und führe aus:

```powershell
cd frontend
python -m http.server 5500
```

Öffne `http://127.0.0.1:5500/register.html`. Registriere einen **fiktiven** Testnutzer. Manche JavaScript-Bibliotheken werden über CDNs geladen, daher kann Internetzugang nötig sein.

## Hinweise

- Verwende niemals echte Kundendaten, Identitätsdokumente oder reale Passwörter zum Testen.
- Das Projekt ist ein lokaler Studienprototyp und nicht für die Bereitstellung im öffentlichen Internet vorbereitet.
- Wenn Node.js-Abhängigkeiten fehlen, prüfe, ob `npm ci` ohne Fehlermeldung abgeschlossen wurde.
