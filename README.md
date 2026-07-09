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
2. **Abstimmen** — eine Stimme pro Person und Idee.
3. **Crew bilden** — per „Ich mach mit" tritt man einer Idee mit einer Rolle bei.
   Die Idee wechselt dann automatisch auf *Crew gesucht*.
4. **Bauen** — beim Hackathon. Status wandert bis *Gebaut*.

Wer keine Idee hat, nutzt den **Ideen-Zünder**: drei Würfel für Abteilung,
Schmerzpunkt und Werkzeug ergeben eine Frage zum Weiterdenken, die sich per Klick
in eine vorausgefüllte Einreichung verwandelt.

## Datenhaltung

Bewusst backend-frei, wie [VibeFeedback](https://github.com/CeeKay1901/vibefeedback):
Die Ideen liegen im `localStorage` des jeweiligen Browsers, nichts geht an einen Server.

Geteilt wird über **JSON-Export/Import** im Fußbereich. Der Import überschreibt nicht,
sondern führt zusammen: Stimmen werden vereinigt (eine pro Person), Crew-Mitglieder ergänzt,
ein fortgeschrittener Status gewinnt. So kann eine Person die Exporte aller Teilnehmenden
einsammeln und hat den Gesamtstand.

Für einen Hackathon mit vielen Einreichenden ist das die Krücke, nicht die Lösung.
Der nächste Schritt ist eine kleine Datenbank hinter Coolify.

**Markdown-Export** gibt die nach Stimmen sortierte Ideenliste aus — die Vorlage fürs Kickoff-Meeting.

## Anpassen

Alles steckt in `index.html`, keine Abhängigkeiten, kein Build.

| Was | Wo im Skript |
|---|---|
| Hackathon-Datum (Countdown) | `HACKATHON_DATE` |
| Tracks | `TRACKS`, `TRACK_GROUPS` |
| Abteilungen | `DEPTS` |
| Status-Stufen | `STATUSES` |
| Beispiel-Ideen | `SEED` |
| Würfel des Ideen-Zünders | `SPARK_PAINS` |

## Verwandt

- **`/ideen-radar`** — Claude-Code-Skill, der laufend neue, konkrete Bau-Ideen für die
  AI-Transformation generiert und sich merkt, was schon vorgeschlagen wurde.
- **[pilot Skill Marketplace](https://github.com/CeeKay1901/pilot-skillmarkt)** — der Katalog der Skills.
- **[VibeFeedback](https://github.com/CeeKay1901/vibefeedback)** — Klick-Feedback auf Prototypen.

## Hinweis

Öffentliches Repo mit internen Inhalten (`noindex` + `robots.txt` halten Suchmaschinen fern,
keine Menschen). Die Namen in den Beispiel-Ideen sind erfunden — bis auf Christopher Kipp.
