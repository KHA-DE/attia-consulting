# Project Context: attia-consulting

## Zweck
Website von Attia Consulting (Karim H. Attia, Strategieberatung seit 1989).
Single-Page, zweisprachig DE/EN, deployed via GitHub Pages.

## Architektur-Stand (2026-07-24)
- Ursprung: Claude-Design-Export. Handoff entpackt unter
  `design/design_handoff_website/` (design_system mit Tokens/Komponenten/Assets,
  README, plus die zwei HTML-Formen unter reference/).
- `reference/website.html` (24 KB): lesbare React/JSX-Quelle mit dem vollen
  Inhalt und der Logik, ABER nicht standalone lauffaehig (verweist auf fehlende
  `_ds_bundle.js`, CDN React/Babel, Pfade passen nicht). Wertvoll als Inhalts- und
  Stil-Referenz.
- `reference/website-standalone.html` (2 MB) = das deployte `index.html`, ein
  selbstpackendes Bundle (Payload als escapter JS-String). NICHT von Hand
  editierbar.
- ENTSCHEIDUNG: eigene, dependency-freie `index.html` als Arbeitsquelle aufbauen
  (Inhalt + Stil aus dem Handoff), damit ohne Design-Tool pflegbar.

## Inhalt (aus website.html verifiziert)
- Sektionen: Header (Hamburger < 700px), Hero, Leistungen (3 Karten aufklappbar),
  Band (Kennzahlen + Technologiewellen + Kernbranchen), Ueber Karim, Wall
  (Stationen), Kontakt (Formular), Footer, Scroll-Fab.
- Technologiewellen (DE): Datenbanken, Internet, Internet der Dinge, Kuenstliche
  Intelligenz. Kernbranchen: ERP, Marketing & Advertising, Health, Sustainability.
- Wall/Stationen (17, mit Kurz-Zuordnung): Xenion, Isobar, Dentsu Aegis Network,
  nugg.ad, Deutsche Post DHL, UBIRCH, IBM, BMG / RKI, GOVERNIFY, Coalition-X,
  Open Prometheus, IAB Europe, IAB US, BVDW, AGOF, agma, ZIA e.V.
- Kontakt: +49 172 4235533, karim@attia.consulting, Gorch-Fock-Haus, Breite
  Strasse 159, 22767 Hamburg. USt-IdNr. DE247412700.

## Offene Aufgaben
- Eigene index.html aufbauen (self-contained, DE/EN-Toggle, Hamburger, Karten,
  Formular, Fab) - Mobil + Desktop verifiziert.
- Bei den Technologiewellen "Datenbanken" um Client/Server ergaenzen.
- Wall-Stationen: monochrome (helle) Logos statt Text einbetten (dunkle Sektion).
