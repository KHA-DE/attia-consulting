# Session History

Context between sessions for attia-consulting.

---

## Session: 2026-07-24 - Stationen-Wall zu interaktivem Beziehungsnetz

### Summary
Die flache Logo-Wall der Stationen-Sektion durch ein interaktives SVG-Beziehungsnetz
ersetzt und live gepusst. Knoten = monochrome Logos, Kanten = Karims tatsaechliche
Beziehungen (Gruendungen, Exits, Gremien), ATTIA als zentrale Nabe.

### Umgesetzt (live)
- 19 monochrome weisse Logos kuratiert (assets/logos/), Sourcing per Logo.dev,
  Wikimedia Special:FilePath und eigenen Dateien; Mono-Pipeline in
  dev-environment/_logowork/mono.py (mehrere Keying-Modi: default/darkink/keywhite).
- Interaktives Netz in index.html: N (21 Knoten inkl. FOMA-Textknoten + ATTIA-Kern),
  EDGES (23 Kanten, Karims exakte Struktur), CLUSTERS (4 Labels: AdTech-Aera,
  Standards & Verbaende, Pandemie & Trust, Aktuelle Ventures), netSVG(lang).
  Hover/Tap hebt Kanten + Nachbarn hervor, dimmt Rest (mount()-Interaktivitaet,
  guarded by .netsvg).
- Zentrale Nabe: statt rotem ATTIA-Kreis das Consulting-Netzwerk-Logo
  (assets/logos/attia.png). Dunkeltaugliche Variante gebaut (Netz weiss, zentrale
  Figur Markenrot) via _logowork/attia_net.py.
- Verifiziert (Playwright, localhost): Desktop 1280 + Mobil 390 = 0 horizontaler
  Ueberlauf; 21 Knoten/23 Kanten/20 Bilder geladen; Interaktion korrekt; nur
  favicon-404. Karim gezeigt (Ruhe- + Aktivzustand), OK, dann gepusst.

### Entscheidungen
- Netz statt Raster: erzaehlt die Beziehungen statt nur Namen zu listen.
- Nabe = echtes Consulting-Logo (ist selbst ein Personen-Netz), thematisch stimmig.

### Offen
- nettest.html (Prototyp) geloescht. Mobil ist das Netz gestaucht/klein aber
  lesbar + tap-bar; ggf. spaeter eine mobil-optimierte Variante erwaegen.

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
