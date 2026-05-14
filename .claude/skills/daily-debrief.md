---
name: daily-debrief
description: Tägliches Morgenbriefing für David. Zeigt den aktuellen Stand aller relevanten Projekte und Bereiche und schlägt 5 sinnvolle To-dos für den Tag vor. Aufrufen mit /daily-debrief.
---

# Daily Debrief Skill

Wenn dieser Skill aufgerufen wird, führe die folgenden Schritte aus und präsentiere am Ende ein kompaktes, klares Morgenbriefing.

## Schritt 1 — Dateien einlesen

Lese parallel:

1. Alle `.md` Dateien in `02 Projekte/` (aktive Projekte)
2. `03 Bereiche/BYTC/BYTC.md`, `03 Bereiche/BYTC/BYTC Strategie.md`, `03 Bereiche/BYTC/BYTC Gründung.md` (falls vorhanden)
3. Alle `.md` Dateien in `03 Bereiche/Uni/` (Uni-Module)
4. Die aktuellste Daily Note in `05 Daily Notes/` (nach Dateiname sortiert, Format YYYY-MM-DD.md)
5. `To Do.md` im Vault-Root (falls vorhanden)

## Schritt 2 — Filtern

Zeige nur Projekte/Bereiche an, bei denen **mindestens eine** dieser Bedingungen zutrifft:

- Es gibt offene To-dos `- [ ]` mit einem Datum in den nächsten 14 Tagen
- Es gibt offene To-dos ohne Datum, die aktiv weitergemacht werden sollten
- Der Status ist `aktiv` und es gibt konkrete nächste Schritte
- Es gibt ein Datum/Deadline in der Datei, das in den nächsten 30 Tagen liegt

**Nicht zeigen:**
- Projekte mit Status `abgeschlossen` oder `pausiert`
- Module oder Projekte ohne jegliche offene Aufgaben oder relevante Deadlines
- Reine Referenz-/Archivdateien

## Schritt 3 — Briefing ausgeben

Formatiere das Briefing so:

```
☀️ Guten Morgen, David — [Wochentag], [Datum]

---

## Projekte & Bereiche

### [Projektname]
**Status:** [ein Satz was gerade läuft]
**Nächstes:** [die 1-2 wichtigsten offenen Punkte]
**Deadline:** [falls relevant]

[weitere Projekte nach gleichem Schema]

---

## 5 To-dos für heute

1. [konkrete, umsetzbare Aufgabe]
2. [konkrete, umsetzbare Aufgabe]
3. [konkrete, umsetzbare Aufgabe]
4. [konkrete, umsetzbare Aufgabe]
5. [konkrete, umsetzbare Aufgabe]

---
[Optionaler kurzer Satz: z.B. auf was heute besonders zu achten ist]
```

## Regeln für die To-do-Vorschläge

- **Konkret und umsetzbar** — nicht "BYTC weiterplanen" sondern "Konzept für Phase 0 Marktanalyse in [[03 Bereiche/BYTC/BYTC Strategie]] starten"
- **Priorisiert nach Deadline** — was bald fällig ist kommt zuerst
- **Mix aus Bereichen** — nicht alle 5 aus demselben Projekt
- **Realistisch für einen Tag** — keine Tasks die Wochen dauern
- **Wikilinks nutzen** — relevante Dateien verlinken damit David direkt navigieren kann

## Stil

- Kein Blabla, kein Padding
- Deutsch
- Direkt, klar, auf den Punkt
- Nicht jedes Projekt aufzählen — nur die, bei denen heute etwas relevant ist
- Bei Uni: Deadlines in den nächsten 2 Wochen immer zeigen
