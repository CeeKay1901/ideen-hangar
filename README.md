# Ideen-Hangar

Das Hackathon-Ideenboard der Citizen-Coding-Initiative der pilot Agenturgruppe.
Kolleg:innen reichen ein, was sie im Arbeitsalltag nervt — die Ideen werden bewertet,
bekommen ein Team und werden beim Hackathon gebaut.

**Live:** https://ceekay1901.github.io/ideen-hangar/

## Drei Tracks

Jede Idee wird einem Werkzeug zugeordnet — als Vermutung, die beim Kickoff gemeinsam geprüft wird.

| Track | Werkzeug | Kommt raus |
|---|---|---|
| **Langdock** | Agents, Workflows | Assistenten und Automationen, ohne eine Zeile Code. DSGVO-konform, EU-gehostet — der Ort für alles mit Kundendaten. |
| **Claude Code** | Webapps, Skills | Echte Tools mit Link, gehostet über Coolify. Skills landen im Skill-Marktplatz. |
| **Claude Design** | Prototypen, Decks | Alles Visuelle im pilot-Design-System. |

## Wie es funktioniert

1. **Idee einreichen** — beschrieben wird zuerst das *Problem*, nicht die Lösung.
   Die Lösungsidee ist optional; wer sein Problem benennen kann, kann mitmachen.
   Beim Tippen des Titels warnt der Hangar, wenn eine ähnliche Idee schon existiert.
2. **Abstimmen** — eine Stimme pro Person und Idee.
3. **Team bilden** — per „Ich mach mit" tritt man einer Idee mit einer Rolle bei.
   Die Idee wechselt dann automatisch auf *Team gesucht*.
4. **Bauen** — beim Hackathon. Den Status darf nur das Team der jeweiligen Idee ändern.

Wer keine Idee hat, nutzt den **Ideen-Zünder**: drei Würfel für Abteilung,
Schmerzpunkt und Werkzeug ergeben eine Frage zum Weiterdenken, die sich per Klick
in eine vorausgefüllte Einreichung verwandelt.

Wer eine Idee eingereicht hat, kann sie später **bearbeiten oder löschen**. Der Filter
*„Von mir"* zeigt alles, woran man beteiligt ist.

## Kategorien

Jede Idee bekommt eine Kategorie. Sie beschreibt, **was die Idee bewirkt** — im Unterschied
zum Track, der beschreibt, **womit sie gebaut wird**.

| | Kategorie | Bedeutung |
|---|---|---|
| ⏱ | Zeit zurückholen | Wiederkehrende Handarbeit, die eine Maschine übernehmen könnte |
| 🔎 | Wissen finden | Informationen, die verstreut sind und jedes Mal neu gesucht werden |
| ✓ | Fehler vermeiden | Prüfen, was sonst jemand übersieht — vor der Abgabe |
| 🔄 | Formate übersetzen | Excel zu Slides, Zahlen zu Klartext, Daten zu Text |
| 🤝 | Zusammenarbeit | Abstimmung, Übergaben, Onboarding, Wissen teilen |
| 🏆 | Kunde & Pitch | Neues Geschäft gewinnen, Kunden überzeugen |
| · | Noch offen | Standard — niemand wird gezwungen, sich festzulegen |

Ideen aus älteren Board-Ständen landen sichtbar unter *„Noch offen"*, statt still einer
falschen Kategorie zugeordnet zu werden.

## Das Kartendeck

Am Hackathon-Tag hilft kein Bildschirm. Über **„Karten drucken"** entsteht eine A4-Druckvorlage:
vier **Idea Cards** pro Blatt, jede zum Ausschneiden. Wer ohne eigene Idee dasitzt, zieht eine
Karte vom Stapel und baut, was darauf steht. Die Nummer oben führt zurück zur Idee im Board.

Jede Karte trägt Kategorie-Kopf mit Symbol, Titel, Problem, Track, geschätzten Aufwand,
Abteilung, Einreicher:in und die Stimmenzahl. Wildcards bekommen einen gelben Rahmen.

Drei Auswahlmöglichkeiten:

- **Gute Ziehkarten** (Standard) — noch nicht gebaut, noch kein Team.
- **Was gerade im Board steht** — die aktuell gefilterte Auswahl, z. B. nur eine Kategorie.
- **Alle Ideen** — inklusive der bereits gebauten.

Der Dialog zeigt vorab, wie viele Karten, Blätter und Kategorien herauskommen, plus eine
Vorschau. **Hintergrundgrafiken müssen in den Druckeinstellungen aktiviert sein**, sonst
bleiben die Kategorie-Köpfe weiß — die Karten funktionieren dann trotzdem, weil jede
Kategorie neben der Farbe auch ein Symbol und ihren Namen trägt. Auf dem Papier werden
gedämpftere Farbtöne benutzt als auf dem Bildschirm (`PRINT_HEX`), damit weiße Schrift
auf dem Kategorie-Kopf lesbar bleibt.

## Oberfläche

Dunkle Produkt-Oberfläche mit einem Akzent (pilot-Gelb) und Kategorien als Leuchtfarben.

- **Command-Palette** mit <kbd>⌘K</kbd> / <kbd>Strg+K</kbd> — alle Aktionen ohne Maus erreichbar.
- **Kürzel**: <kbd>N</kbd> neue Idee, <kbd>/</kbd> Suche, <kbd>R</kbd> Ideen-Zünder würfeln.
- **Einreichen in vier Schritten** statt eines langen Formulars: Problem → Kategorie → Werkzeug → Du.
  Am Ende wird die Idea Card sichtbar „gedruckt".
- Cursor-Spotlight auf Karten, Zähler zählen hoch, Scroll-Reveal, Spring-Kurven.
- Alles respektiert `prefers-reduced-motion`. Der Inhalt hängt nie an einer Animation:
  Fällt der IntersectionObserver aus, wird alles sofort sichtbar.

## Anpassen

Alles steckt in `index.html`, keine Abhängigkeiten, kein Build.

| Was | Wo im Skript |
|---|---|
| Hackathon-Datum (Countdown) | `HACKATHON_DATE` |
| Tracks | `TRACKS`, `TRACK_CARDS` |
| Kategorien (Name, Symbol, Farbe) | `CATEGORIES` + `--c-*` in den CSS-Tokens |
| Abteilungen | `DEPTS` |
| Status-Stufen | `STATUSES` |
| Beispiel-Ideen | `SEED` |
| Würfel des Ideen-Zünders | `SPARK_PAINS` |
| Druckfarben der Kategorien | `PRINT_HEX` |
| Karten pro Druckseite | `PRO_SEITE` |

## Verwandt

- **`/ideen-radar`** — Claude-Code-Skill, der laufend neue, konkrete Bau-Ideen für die
  AI-Transformation generiert und sich merkt, was schon vorgeschlagen wurde.
- **[pilot Skill Marketplace](https://github.com/CeeKay1901/pilot-skillmarkt)** — der Katalog der Skills.
- **[VibeFeedback](https://github.com/CeeKay1901/vibefeedback)** — Klick-Feedback auf Prototypen.

## Hinweis

Öffentliches Repo mit internen Inhalten (`noindex` + `robots.txt` halten Suchmaschinen fern,
keine Menschen). Die Namen in den Beispiel-Ideen sind erfunden — bis auf Christopher Kipp.
