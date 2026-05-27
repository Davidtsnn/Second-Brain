---
tags: [jannes, kunden, aktiv]
status: aktiv
date: 2026-05-26
---

# Aktive Kunden

Laufende Verhandlungen und Deals. Sobald ein Deal final ist und ein konkretes Projekt startet, wandert er nach [[Projekte Übersicht]].

## Übersicht

```dataview
TABLE WITHOUT ID
	file.link AS "Kunde",
	preis AS "Preis",
	leistung AS "Leistung",
	status AS "Status"
FROM "03 Bereiche/Jannes Videograf/Kunden"
WHERE contains(tags, "aktiv-kunde")
SORT file.name ASC
```

## Kunden

- [[Simon Hochzeits-Post]]
- [[Andreas Physio Berner]]
