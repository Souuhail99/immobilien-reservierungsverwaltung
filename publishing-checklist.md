# Checkliste vor GitHub-Veröffentlichung

- [ ] Zustimmung der weiteren Teammitglieder zur Veröffentlichung einholen.
- [ ] Persönliche Daten und Zugangsdaten aus Dateien, Bildern und Git-Historie entfernen.
- [ ] `backend/db.json` (Benutzer, Reservationen, Hashes) niemals hochladen.
- [ ] `backend/node_modules/` und private Export-/Upload-Dateien ausschließen.
- [ ] Nur `backend/db.example.json` mit **leeren Arrays** bereitstellen.
- [ ] Eigenes `JWT_SECRET` als Umgebungsvariable setzen; niemals ins Repository schreiben.
- [ ] Die Original-Spezifikation und Architektur-PDFs nicht unverändert veröffentlichen: Deckblätter enthalten persönliche Daten des Teams.
- [ ] Funktionalität und Sicherheitsstatus ehrlich beschreiben: kein Produktions-Deployment.
- [ ] Vor dem Umschalten auf **Public** alle hochgeladenen Dateien prüfen.

## Gezielte Sicherheitsanpassungen am Backend-Code im Paket

1. Der unsichere vordefinierte JWT-Demoschlüssel wurde entfernt und eine Umgebungsvariable verpflichtend gemacht.
2. Bei der Erstellung von Reservierungen können `userId` und `id` nicht mehr über den Request-Body vorgegeben werden.
3. Beim Anlegen neuer Unterkünfte wird die Server-ID ebenfalls zuletzt gesetzt, sodass sie nicht überschrieben werden kann.

Diese Schritte sind **keine vollständige Sicherheitsprüfung**.
