# Ideen-Hangar

Das Hackathon-Ideenboard der Citizen-Coding-Initiative der pilot Agenturgruppe.
Kolleg:innen reichen ein, was sie im Arbeitsalltag nervt — die Ideen werden bewertet,
bekommen eine Crew und werden beim Hackathon gebaut.

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
3. **Crew bilden** — per „Ich mach mit" tritt man einer Idee mit einer Rolle bei.
   Die Idee wechselt dann automatisch auf *Crew gesucht*.
4. **Bauen** — beim Hackathon. Den Status darf nur die Crew der jeweiligen Idee ändern.

Wer keine Idee hat, nutzt den **Ideen-Zünder**: drei Würfel für Abteilung,
Schmerzpunkt und Werkzeug ergeben eine Frage zum Weiterdenken, die sich per Klick
in eine vorausgefüllte Einreichung verwandelt.

Wer eine Idee eingereicht hat, kann sie später **bearbeiten oder löschen**. Der Filter
*„Von mir / meine Crew"* zeigt alles, woran man beteiligt ist.

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

## Der Lostopf

Am Hackathon-Tag hilft kein Bildschirm. Über **„🎟 Lose drucken"** entsteht eine A4-Druckvorlage:
sechs Lose pro Blatt, jedes zum Ausschneiden. Wer ohne eigene Idee dasitzt, zieht eines aus dem
Topf und baut, was darauf steht.

Jedes Los trägt Kategorie-Band, Titel, Problem, Track, geschätzten Aufwand und die Stimmenzahl.
Wildcards bekommen ein gelbes Band und einen gelben Rahmen.

Drei Auswahlmöglichkeiten:

- **Gute Lostopf-Kandidaten** (Standard) — noch nicht gebaut, noch keine Crew. Genau das,
  was jemand übernehmen kann.
- **Was gerade im Board steht** — die aktuell gefilterte Auswahl, z. B. nur eine Kategorie.
- **Alle Ideen** — inklusive der bereits gebauten.

Der Dialog zeigt vorab, wie viele Lose, Blätter und Kategorien dabei herauskommen, und blendet
eine Vorschau ein. **Hintergrundgrafiken müssen in den Druckeinstellungen aktiviert sein**,
sonst bleiben die Kategorie-Bänder weiß — die Lose funktionieren dann trotzdem, weil jede
Kategorie neben der Farbe auch ein Symbol und ihren Namen trägt.

## Für Nicht-Techniker gebaut

Die Zielgruppe sind Mediaplaner:innen, Texter:innen und Strateg:innen — nicht Entwickler.
Entsprechend:

- **Kein Fachjargon als Einstiegshürde.** Die Tracks tragen ein sichtbares
  „✓ Ohne Programmieren"-Signal, wo es zutrifft (Langdock, Claude Design).
- **Das Formular fragt nach dem Problem, nicht nach der Lösung.** Aufwand steht
  standardmäßig auf „Keine Ahnung" — niemand muss schätzen, was er nicht schätzen kann.
- **Keine nativen Browser-Dialoge.** Name, Rolle und Bestätigungen laufen über
  gestaltete Dialoge im pilot-Design.
- **Getippter Text geht nicht verloren.** Wer das Formular mit Inhalt schließt, wird gefragt.

## Barrierefreiheit

- Skip-Link zum Board, vollständige Tastatur-Bedienung, Fokusfalle in Dialogen.
- Keine verschachtelten interaktiven Elemente (die Karte nutzt das Stretched-Link-Muster).
- Trefferzahl der Filter wird als `aria-live`-Region angesagt.
- Alle Touch-Ziele mindestens 44 × 44 px; `prefers-reduced-motion` wird respektiert.
- Status und Track sind nie nur über Farbe kodiert, immer auch über Text.

## Datenhaltung

Bewusst backend-frei, wie [VibeFeedback](https://github.com/CeeKay1901/vibefeedback):
Die Ideen liegen im `localStorage` des jeweiligen Browsers, nichts geht an einen Server.

Geteilt wird über **JSON-Export/Import** im Fußbereich. Der Import überschreibt nicht,
sondern führt zusammen: Stimmen werden vereinigt (eine pro Person), Crew-Mitglieder ergänzt,
ein fortgeschrittener Status gewinnt. So kann eine Person die Exporte aller Teilnehmenden
einsammeln und hat den Gesamtstand.

Damit niemand seine Arbeit verliert, blendet der Hangar ein **Export-Banner** ein, sobald
man mit ungesicherten Änderungen aus einem anderen Tab zurückkommt.

Für einen Hackathon mit vielen Einreichenden ist das die Krücke, nicht die Lösung.
Der nächste Schritt ist eine kleine Datenbank hinter Coolify.

**Markdown-Export** gibt die nach Stimmen sortierte Ideenliste aus — die Vorlage fürs Kickoff-Meeting.

## Anpassen

Alles steckt in `index.html`, keine Abhängigkeiten, kein Build.

| Was | Wo im Skript |
|---|---|
| Hackathon-Datum (Countdown) | `HACKATHON_DATE` |
| Tracks | `TRACKS`, `TRACK_GROUPS` |
| Kategorien (Name, Symbol, Farbe) | `CATEGORIES` + `--cat-*` in den CSS-Tokens |
| Abteilungen | `DEPTS` |
| Status-Stufen | `STATUSES` |
| Beispiel-Ideen | `SEED` |
| Würfel des Ideen-Zünders | `SPARK_PAINS` |
| Lose pro Druckseite | `LOSE_PRO_SEITE` |

## Verwandt

- **`/ideen-radar`** — Claude-Code-Skill, der laufend neue, konkrete Bau-Ideen für die
  AI-Transformation generiert und sich merkt, was schon vorgeschlagen wurde.
- **[pilot Skill Marketplace](https://github.com/CeeKay1901/pilot-skillmarkt)** — der Katalog der Skills.
- **[VibeFeedback](https://github.com/CeeKay1901/vibefeedback)** — Klick-Feedback auf Prototypen.

## Hinweis

Öffentliches Repo mit internen Inhalten (`noindex` + `robots.txt` halten Suchmaschinen fern,
keine Menschen). Die Namen in den Beispiel-Ideen sind erfunden — bis auf Christopher Kipp.
