---
tags: [jannes, projekte]
status: aktiv
date: 2026-05-26
---

# Projekte Übersicht

Konkrete Produktionen mit klarem Auftrag. Sobald ein Kunde zugesagt hat und gedreht/produziert wird, kommt der Job hier rein.

## Laufende Projekte

```dataview
TABLE WITHOUT ID
	file.link AS "Projekt",
	kunde AS "Kunde",
	deadline AS "Deadline",
	status AS "Status"
FROM "03 Bereiche/Jannes Videograf/Projekte"
WHERE status != "abgeschlossen"
SORT deadline ASC
```

## Abgeschlossen

```dataview
TABLE WITHOUT ID
	file.link AS "Projekt",
	kunde AS "Kunde",
	preis AS "Preis"
FROM "03 Bereiche/Jannes Videograf/Projekte"
WHERE status = "abgeschlossen"
SORT file.mtime DESC
```

## Aktuelle Pipeline

Sobald Verhandlungen abgeschlossen sind, hier hinzufügen:
- Simon (5 Reels, falls 300€ angenommen)
- Andreas Physio (Clips, falls bestätigt)
- Chris & Lea (800 Bilder Bearbeitung)
