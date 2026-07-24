# attia-consulting — Projekt-Regeln

Website von Attia Consulting (attia.consulting). Statische Single-Page-Site,
deployed via GitHub Pages (Repo KHA-DE/attia-consulting, Branch main, Root).
Kontext in `.claude/context.md`, Historie in `.claude/history.md`.

## Source of Truth
- Die Seite wird als EINE selbst-enthaltene `index.html` gepflegt: kein Build,
  keine externe Abhaengigkeit, keine CDN. Das Claude-Design-Handoff unter
  `design/` war der Kickoff und bleibt Referenz, nicht die Arbeitsquelle.
- Das alte selbstpackende Bundle NICHT von Hand editieren (der Bundler
  ueberschreibt Aussen-Edits).

## Arbeitsweise (hart, aus Erfahrung)
- Jede Aenderung lokal am 390px- UND am Desktop-Viewport pruefen.
- Karim das Ergebnis zeigen und ERST nach seinem OK live pushen (show-then-push,
  nie push-then-show auf der oeffentlichen Seite).

## Deploy
- Push auf `main` -> GitHub Pages deployt automatisch.
  Live: https://kha-de.github.io/attia-consulting/ (Ziel-Domain attia.consulting).

## Prosa
- Seite ist zweisprachig DE/EN. Keine Gedankenstriche, keine KI-/Tool-Referenzen
  im ausgelieferten Inhalt. Autor aller Dateien: Karim H. Attia.
