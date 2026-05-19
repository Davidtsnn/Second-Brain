---
name: day-planner
description: Interaktive Tagesplanung nach dem Daily Debrief. Liest offene Todos aus Obsidian, Kalender und Mails, bespricht mit David welche Aufgaben er heute macht, verschiebt oder skippt, und erstellt einen konkreten Tagesplan mit Zeitblöcken. Aufrufen mit /day-planner.
---

# Day Planner Skill

## Wo dieser Skill verwendet wird

**Primär: claude.ai im Browser** — dort hat Claude Zugriff auf:
- ✅ Google Calendar MCP (Termine abrufen)
- ✅ Gmail MCP (Mails lesen)
- ✅ Obsidian Vault (über den Obsidian MCP Connector)

**Alternativ: Claudian Plugin in Obsidian** — nur Vault-Zugriff, kein Kalender/Mail.

---

Wenn dieser Skill aufgerufen wird, führe die folgenden Schritte durch.

## Schritt 1 — Kontext laden

Lese aus dem Obsidian Vault (via Obsidian MCP oder direkt):
1. `To Do.md` im Vault-Root
2. Alle `.md` Dateien in `02 Projekte/`
3. Alle `.md` Dateien in `03 Bereiche/Uni/`
4. `03 Bereiche/BYTC/BYTC.md` und `02 Projekte/BYTC Gründung.md`
5. Die neueste Datei in `05 Daily Notes/` falls vorhanden

## Schritt 2 — Kalender abrufen

Rufe über Google Calendar MCP alle Termine von **heute und morgen** ab.
- Zeige jeden Termin mit Uhrzeit, Titel und Dauer
- Markiere Termine die Vorbereitung brauchen

## Schritt 3 — Mails prüfen

Rufe über Gmail MCP die **ungelesenen Mails der letzten 24 Stunden** ab (max. 10).
- Zeige nur Mails die heute Aktion erfordern könnten (Absender + Betreff)
- Ignoriere Newsletter, automatische Benachrichtigungen etc.

## Schritt 4 — Briefing ausgeben

Präsentiere David eine kompakte Übersicht:

```
📋 Tagesplanung — [Wochentag], [Datum]

TERMINE HEUTE
[Zeit] — [Terminname]
[Zeit] — [Terminname]
(oder: Keine Termine gefunden / Kalender nicht verbunden)

OFFENE AUFGABEN
🔴 Dringend (Deadline heute/morgen):
  • [Aufgabe] — [Projekt]

🟡 Diese Woche:
  • [Aufgabe] — [Projekt]

⚪ Kein fixes Datum:
  • [Aufgabe] — [Projekt]

MAILS DIE HEUTE BEACHTET WERDEN SOLLTEN
  • [Absender]: [Betreff]
(oder: Keine / Gmail nicht verbunden)

Welche Aufgaben möchtest du heute angehen?
```

## Schritt 5 — Interaktive Planung

Warte auf Davids Antwort. Er wird sagen welche Aufgaben er:
- **Heute macht** — diese kommen in den Tagesplan
- **Verschiebt** — frage auf wann, trage es in die entsprechende Projektdatei ein
- **Skippt / irrelevant** — abhaken oder aus der Liste entfernen
- **Neu hinzufügt** — Aufgaben die noch nicht in den Dateien stehen

Bestätige jede Entscheidung kurz und frage dann nach dem nächsten Punkt.

## Schritt 6 — Tagesplan mit Zeitblöcken erstellen

Wenn David alle Aufgaben durchgegangen ist, erstelle einen konkreten Tagesplan.

**Logik für Zeitblöcke:**
- Trage Kalendertermine als fixe Blöcke ein
- Plane Aufgaben in die freien Zeitfenster — realistische Zeitschätzung pro Aufgabe
- Puffer zwischen Terminen und Aufgaben einplanen (15-30 Min)
- Schwierige/kreative Aufgaben in den Morgen, einfachere nachmittags
- Nicht mehr als 6 Stunden echte Arbeitszeit einplanen

**Format:**
```
🗓️ Dein Tag — [Datum]

08:00 — 09:30  [Aufgabe 1]
09:30 — 10:00  Puffer / Mails
10:00 — 11:00  [Termin aus Kalender]
11:00 — 12:30  [Aufgabe 2]
12:30 — 13:30  Mittagspause
13:30 — 15:00  [Aufgabe 3]
...

Verschoben auf [Datum]: [Aufgaben]
Heute nicht: [Aufgaben]
```

## Schritt 7 — Daily Note erstellen/updaten

Schreibe den fertigen Tagesplan in die Daily Note `05 Daily Notes/YYYY-MM-DD.md`:
- Falls die Datei noch nicht existiert: erstelle sie mit dem Tagesplan
- Falls sie schon existiert: füge den Tagesplan oben ein

**Format der Daily Note:**

```markdown
---
tags: [daily]
date: YYYY-MM-DD
---

# [Wochentag], [Datum]

## Tagesplan

[Zeitplan hier]

## Notizen

## Log
```

## Stil & Regeln

- Direkt und klar, kein Blabla
- Deutsch
- David entscheidet — nicht bevormunden
- Immer konkrete Uhrzeiten vorschlagen, nicht nur Reihenfolge
- Wenn Kalender oder Gmail fehlen: trotzdem einen guten Plan machen
- Am Ende des Plans immer fragen: "Passt das so oder soll ich etwas anpassen?"
