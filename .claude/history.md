# Session History

Context between sessions for attia-consulting.

---

## Session: 2026-07-23/24 - Website als eigenes Projekt aufgesetzt

### Summary
Website (KHA-DE/attia-consulting, GitHub Pages) als eigenstaendiges Projekt unter
BasePath_Attia etabliert. Claude-Design war der Kickoff; ab jetzt eigene,
dependency-freie index.html als Arbeitsquelle.

### Verlauf
- 23.07. nachts: schneller Mobil-Patch direkt ins 2-MB-Bundle gespritzt -> brach
  auf Karims echtem iPhone die Kopfzeile (Nav-Ueberlappung), sofort revertiert.
  Lehre: keine Bundle-Hacks, und auf der oeffentlichen Seite show-then-push.
- 24.07.: neuer Claude-Design-Export (Hamburger-Menue, einspaltige Karten) am
  390px getestet - sauber bis auf ~9px Rest-Ueberlauf der Wall-Kacheln. Nicht
  gepusht. Handoff-ZIP entpackt nach design/. Quelle (website.html) komplett
  gelesen, Architektur analysiert (siehe context.md).
- Hygiene angelegt (CLAUDE.md, context.md, history.md).

### Entscheidungen
- Source of Truth = eigene self-contained index.html (kein Build, keine CDN),
  Inhalt/Stil aus dem Handoff. Design-Tool nur Kickoff.

### Umgesetzt (24.07., live)
- Eigene dependency-freie index.html gebaut (Vanilla-JS statt React/CDN), Inhalt
  und Look originalgetreu aus dem Handoff. Client/Server bei den Technologiewellen
  ergaenzt. Menue erweitert um Profil (das 1989-Band) + Stationen als Anker;
  Nav-Links schliessen das Handy-Menue. Desktop + 390px verifiziert: 0 Ueberlauf.
  Assets nach assets/ kopiert. Basis + Menue live gepusht.
- Nachtrag: Client/Server aus den Wellen wieder entfernt (ist die Architektur der
  Datenbanken-Aera, keine eigene Marktwelle; Erzaehlung bleibt bei vier Wellen).

### Offen
- Wall-Stationen mit monochromen Logos statt Wortmarken: Sourcing offen. Viele der
  17 haben kein sauberes oeffentliches Logo; die eigenen Marken (Governify,
  Coalition-X, Open Prometheus) brauchen von Karim die richtigen Logo-Dateien.
  Drei Wege mit Karim besprochen (einheitliche Wortmarken behalten / echte Logos
  wo sauber + eigene Marken / Ordner mit exakten Dateien).
