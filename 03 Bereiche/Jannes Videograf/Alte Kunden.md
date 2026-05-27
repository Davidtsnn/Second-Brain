---
tags: [jannes, kunden, alt]
status: aktiv
date: 2026-05-26
---

# Alte Kunden

Frühere Kunden von Jannes. Outreach-Liste für Feedback-Kampagne.

## Strategie

Ehrlich und ohne Verkaufsdruck anschreiben. Aufhänger: "Wir stellen uns neu auf, haben ein neues Konzept. Wir wollen euch gar nichts verkaufen, sondern einfach mal eure Meinung dazu hören."

Daraus entstehen organisch:
- Feedback fürs Konzept
- Reaktivierte Aufträge
- Empfehlungen

## Outreach Status

```dataview
TABLE WITHOUT ID
	file.link AS "Kunde",
	angeschrieben AS "Angeschrieben",
	geantwortet AS "Geantwortet",
	status AS "Status"
FROM "03 Bereiche/Jannes Videograf/Kunden"
WHERE contains(tags, "alt-kunde")
SORT angeschrieben DESC
```

## To Do

- [ ] Liste aller Alt-Kunden von Jannes einholen
- [ ] Outreach-Template schreiben
- [ ] Welle 1 verschicken (5-10 Kunden)
- [ ] Antworten auswerten

## Kunden

Hier kommen einzelne Dateien rein sobald Jannes seine Kontaktliste durchgegeben hat.
