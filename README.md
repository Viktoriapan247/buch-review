# Novelle 🔖 – dein digitales Bücherregal

Eine private, mobile-first Lese-App als eine einzige HTML-Datei (`index.html`).
Kein Konto, kein Tracking – alle Daten bleiben im Browser des Geräts (localStorage).

## Funktionen

- **Bücher anlegen** mit Titel, Autor·in, Sprache, Medium (Physisch / Kindle & E-Book / Audible & Hörbuch), Cover-Upload (wird automatisch verkleinert), Genre, Start- und Enddatum
- **Bereits gelesene Bücher nachtragen** – nur mit dem Lesejahr, wenn genaue Daten nicht mehr bekannt sind
- **Mehrere Bücher parallel lesen** – Tab „Aktuell“ mit Lesefortschritt (Seite / Kapitel / Prozent)
- **Buchreihen verbinden** – Reihenname + Bandnummer, weitere Bände werden im Buchdetail verlinkt
- **Beenden-Flow**: Enddatum, Sternebewertung und ein **personalisierter Reflexions-Fragenkatalog** (5–10 Minuten), abgestimmt auf Genre, Medium, Reihe und Lesedauer – inkl. Fragen zu Erzählperspektive und dem, was man für die Zukunft mitnimmt
- **Buch-Chat mit Spoilerschutz**: Gespräch über das Buch schon während des Lesens; die Grenze ist der eingetragene Fortschritt
- **10 Fakten zu Buch & Autor·in** und **Stimmen aus der Lese-Community** nach dem Beenden
- **Bücherregal** mit Suche (auch nach Lesejahr) sowie Filtern nach Jahr, Genre, Medium, Sprache und Reihe, mehrere Sortierungen
- **Wunschliste / Leseliste** und **Empfehlungen** auf Basis des eigenen Regals
- **Statistik**: Bücher pro Jahr, Genres, Medien
- **Backup exportieren / importieren** (JSON) – auch als Brücke zwischen Geräten
- **Helles und dunkles Design** mit zwei wählbaren Farbwelten: „Aura“ (Pink, Orange, Lila, Gelb) und „Nacht“ (Schwarz & Navy), jeweils mit Frosted-Glass-Oberflächen im iOS-Stil und passendem Logo

## KI-Funktionen (optional)

Ohne Konfiguration arbeitet die App im **Begleiter-Modus**: Der Fragenkatalog wird
regelbasiert personalisiert, der Chat stellt Reflexionsfragen.

Unter **Mehr → KI-Verbindung** kann ein Claude-API-Schlüssel hinterlegt werden
(bleibt nur auf dem Gerät). Dann übernehmen echte KI-Aufrufe:

- Buch-Chat mit inhaltlichen Antworten (weiterhin mit striktem Spoilerschutz)
- auf das konkrete Buch zugeschnittener Fragenkatalog
- 10 Fakten, Community-Stimmen, Genre-Einschätzung und Buchempfehlungen

Hinweis: In der geschützten Claude-Artifact-Vorschau sind externe Verbindungen
gesperrt – dort greift automatisch der Begleiter-Modus. Selbst gehostet
(z. B. GitHub Pages) funktionieren die KI-Funktionen mit Schlüssel.

## Nutzung

1. `index.html` in einem Browser öffnen – fertig. Es gibt keinen Build-Schritt.
2. Als „App“ auf dem Handy: Seite im Browser öffnen → „Zum Home-Bildschirm hinzufügen“.
3. Alternativ über GitHub Pages o. Ä. hosten.

## Roadmap / Vormerkungen

- **Optionales Konto & Geräte-Sync**: bewusst vorgemerkt, aber noch nicht umgesetzt.
  Die Datenhaltung ist darauf vorbereitet (ein zentrales JSON-Objekt, Export/Import
  als Austauschformat), sodass später ein Sync-Backend andocken kann.
- Community-Beiträge aus echten Quellen (statt KI-Zusammenfassung)
- Erinnerungen / Leseziele

## Technik

- Eine Datei, kein Framework, keine externen Abhängigkeiten (System-Schriften: SF/Helvetica)
- Datenmodell: `{ books: [...], settings: {...}, recs: [...] }` in `localStorage` (`eselsohr.v1`)
- Design nach Apple-HIG-Prinzipien: Bottom-Tab-Navigation, Touch-Targets ≥ 44 pt,
  Kontraste ≥ 4.5:1, Dynamic-Type-freundliche Skala, Safe-Area-Insets, Light/Dark Mode
