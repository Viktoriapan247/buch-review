# Novelle 🔖 – dein digitales Bücherregal

Eine private, mobile-first Lese-App als eine einzige HTML-Datei (`index.html`).
Kein Konto, kein Tracking – alle Daten bleiben im Browser des Geräts (localStorage).

## Funktionen

- **Bücher anlegen** mit Titel, Autor·in, Sprache, Medium (Physisch / Kindle & E-Book / Audible & Hörbuch), Cover-Upload (wird automatisch verkleinert), Genre, Erscheinungsjahr/-ort, Start- und Enddatum – mit KI-Verbindung füllt Novelle Autor·in, Erscheinungsjahr/-ort, Genre und Reihe automatisch aus, sobald der Titel eingegeben ist
- **Bereits gelesene Bücher nachtragen** – nur mit dem Lesejahr, wenn genaue Daten nicht mehr bekannt sind
- **Mehrere Bücher parallel lesen** – Tab „Aktuell“ mit Lesefortschritt (Seite / Kapitel / Prozent)
- **Buchreihen verbinden** – Reihenname + Bandnummer, weitere Bände werden im Buchdetail verlinkt
- **Beenden-Flow**: Enddatum, Sternebewertung und ein **personalisierter Reflexions-Fragenkatalog** (5–10 Minuten), abgestimmt auf Genre, Medium, Reihe und Lesedauer – inkl. Fragen zu Erzählperspektive und dem, was man für die Zukunft mitnimmt
- **Buch-Chat mit Spoilerschutz**: Gespräch über das Buch schon während des Lesens; die Grenze ist der eingetragene Fortschritt
- **10 Fakten zu Buch & Autor·in** und **Stimmen aus der Lese-Community** nach dem Beenden
- **„Worum ging’s?“ (KI-Erinnerung)**: kurze Zusammenfassung zum Auffrischen – ideal für nachgetragene Bücher vor dem Fragenkatalog
- **Zwischen-Fragenkatalog** für aktuelle Bücher (spoilerfrei, auf den Lesestand bezogen) – Antworten jederzeit bearbeitbar, ebenso der Leseeindruck nach dem Beenden
- **Eigene Zusammenfassung** pro Buch, mit Leitfragen & Tipps und optionalem KI-Entwurf aus den eigenen Stichpunkten
- **Bücherregal** mit Suche (auch nach Lesejahr) sowie Filtern nach Jahr, Genre, Medium, Sprache und Reihe, mehrere Sortierungen
- **Wunschliste / Leseliste** und **Empfehlungen** auf Basis des eigenen Regals
- **Statistik**: Bücher pro Jahr, Genres, Medien
- **Backup exportieren / importieren** (JSON) – auch als Brücke zwischen Geräten
- **Helles und dunkles Design** mit zwei wählbaren Farbwelten: „Aura“ (Pink, Orange, Lila, Gelb) und „Nacht“ (Schwarz & Navy), jeweils mit Frosted-Glass-Oberflächen im iOS-Stil und passendem Logo

## KI-Funktionen (optional)

Ohne Konfiguration arbeitet die App im **Begleiter-Modus**: Der Fragenkatalog wird
regelbasiert personalisiert, der Chat stellt Reflexionsfragen.

Unter **Mehr → KI-Verbindung** kann ein Google-Gemini-API-Schlüssel hinterlegt
werden (kostenlos über [Google AI Studio](https://aistudio.google.com) → „Get API
key“; bleibt nur im Browser/localStorage, nie im Code). Dann übernehmen echte
KI-Aufrufe (Standard-Modell: `gemini-3.5-flash-lite`, schnell und in der
Gratis-Stufe enthalten; alternativ `gemini-3.6-flash` / `gemini-3.7-flash`):

- Buch-Chat mit inhaltlichen Antworten (weiterhin mit striktem Spoilerschutz)
- auf das konkrete Buch zugeschnittener Fragenkatalog
- 10 Fakten, Community-Stimmen, Genre-Einschätzung und Buchempfehlungen

Bei ungültigem Schlüssel oder erreichtem Tageslimit zeigt Novelle eine
verständliche Meldung und fällt automatisch in den Begleiter-Modus zurück.

Hinweis: In der geschützten Claude-Artifact-Vorschau sind externe Verbindungen
gesperrt – dort greift automatisch der Begleiter-Modus. Selbst gehostet
(z. B. GitHub Pages) funktionieren die KI-Funktionen mit Schlüssel; die
Gemini-API erlaubt Aufrufe direkt aus dem Browser (CORS).

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
