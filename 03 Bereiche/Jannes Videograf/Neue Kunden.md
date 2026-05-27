---
tags: [jannes, kunden, neu]
status: aktiv
date: 2026-05-26
---

# Neue Kunden

Frische Leads und Anfragen. Noch im frühen Stadium.

## Übersicht

```dataview
TABLE WITHOUT ID
	file.link AS "Lead",
	quelle AS "Quelle",
	status AS "Status",
	preis AS "Preisidee"
FROM "03 Bereiche/Jannes Videograf/Kunden"
WHERE contains(tags, "neu-kunde")
SORT file.name ASC
```

## Leads

- [[Chris & Lea Hochzeitsbilder]]
- [[Fahrlehrer Lukas]]
- [[Rechtsanwältin Arslan]]
- [[Melina Bauer]] — Connect & Collect (Fitnessstudios)
