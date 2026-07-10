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

Jede Kategorie trägt ein zweibuchstabiges Kürzel wie ein Aktenzeichen. Es steht überall
neben dem ausgeschriebenen Namen — die Karten bleiben also auch schwarzweiß eindeutig.

| | Kategorie | Bedeutung |
|---|---|---|
| ZT | Zeit zurückholen | Wiederkehrende Handarbeit, die eine Maschine übernehmen könnte |
| WS | Wissen finden | Informationen, die verstreut sind und jedes Mal neu gesucht werden |
| QS | Fehler vermeiden | Prüfen, was sonst jemand übersieht — vor der Abgabe |
| FM | Formate übersetzen | Excel zu Slides, Zahlen zu Klartext, Daten zu Text |
| TM | Zusammenarbeit | Abstimmung, Übergaben, Onboarding, Wissen teilen |
| PT | Kunde & Pitch | Neues Geschäft gewinnen, Kunden überzeugen |
| — | Noch offen | Standard — niemand wird gezwungen, sich festzulegen |

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
Kategorie neben der Farbe auch ihr Kürzel und ihren Namen trägt.

## Oberfläche

Kein Dark Mode: **Papier, Tinte und ein Gelb.** Der Bildschirm spricht dieselbe Sprache
wie das gedruckte Kartendeck — weiße Karten mit farbigem Kategorie-Band, schwarzer Fuß,
Haarlinien statt Schatten. Die Kategoriefarben am Bildschirm *sind* die Druckfarben
(`PRINT_HEX` = die `--c-*`-Tokens), es gibt also keine Überraschung beim Ausdruck.
Akzentfarbe ist ausschließlich das pilot-Gelb; es markiert wie ein Textmarker.

- **Command-Palette** mit <kbd>⌘K</kbd> / <kbd>Strg+K</kbd> — alle Aktionen ohne Maus erreichbar.
- **Kürzel**: <kbd>N</kbd> neue Idee, <kbd>/</kbd> Suche, <kbd>R</kbd> Ideen-Zünder würfeln.
- **Einreichen in vier Schritten** statt eines langen Formulars: Problem → Kategorie → Werkzeug → Du.
  Am Ende wird die Idea Card sichtbar „gedruckt".
- Im Hero liegen zwei **echte Karten** aus dem Board — das Produkt zeigt sich selbst.
- Alles respektiert `prefers-reduced-motion`. Der Inhalt hängt nie an einer Animation:
  Fällt der IntersectionObserver aus, wird alles sofort sichtbar.

## Ideen teilen

Jede Idee hat einen **Deep-Link** (`#i/<id>`), erreichbar über „Link kopieren" im Detail —
gedacht für Teams-Chats: Link schicken, Empfänger:in landet direkt in der Idee.
Die Beispiel-Ideen haben stabile IDs, damit ihre Links in jedem Browser funktionieren.
Selbst eingereichte Ideen wandern per JSON-Export/Import mitsamt ID — der Link funktioniert
also bei allen, die den Board-Stand importiert haben; andernfalls erklärt ein Hinweis, warum nicht.

Im Detail lässt sich außerdem **eine einzelne Idea Card drucken**, und Link-Vorschauen
in Teams/Slack zeigen ein eigenes OG-Bild (`og-image.png`).

## Anpassen

Alles steckt in `index.html`, keine Abhängigkeiten, kein Build.

| Was | Wo im Skript |
|---|---|
| Hackathon-Datum (Countdown) | `HACKATHON_DATE` |
| Tracks | `TRACKS`, `TRACK_CARDS` |
| Kategorien (Name, Kürzel, Farbe) | `CATEGORIES` + `--c-*` in den CSS-Tokens |
| Abteilungen | `DEPTS` |
| Status-Stufen | `STATUSES` |
| Beispiel-Ideen | `SEED` |
| Würfel des Ideen-Zünders | `SPARK_PAINS` |
| Druckfarben der Kategorien | `PRINT_HEX` (muss zu `--c-*` passen) |
| Karten pro Druckseite | `PRO_SEITE` |

## Verwandt

- **`/ideen-radar`** — Claude-Code-Skill, der laufend neue, konkrete Bau-Ideen für die
  AI-Transformation generiert und sich merkt, was schon vorgeschlagen wurde.
- **[pilot Skill Marketplace](https://github.com/CeeKay1901/pilot-skillmarkt)** — der Katalog der Skills.
- **[VibeFeedback](https://github.com/CeeKay1901/vibefeedback)** — Klick-Feedback auf Prototypen.

## Hinweis

Öffentliches Repo mit internen Inhalten (`noindex` + `robots.txt` halten Suchmaschinen fern,
keine Menschen). Die Namen in den Beispiel-Ideen sind erfunden — bis auf Christopher Kipp.
