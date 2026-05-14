# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

## Vault Technical Context

**Type:** Obsidian vault — not a software project. There are no build, lint, or test commands.

**AI Integration:** Claudian plugin (`realclaudian` v2.0.14) embeds Claude Code inside Obsidian. Vault root is the working directory. Always use relative paths (never absolute `/Users/...` paths).

**Installed Skills** (`.claude/skills/`): obsidian-markdown, obsidian-bases, json-canvas, obsidian-cli, defuddle, daily-debrief.

## Daily Debrief

Täglich um 7:00 Uhr (Europe/Berlin) läuft ein Remote Agent (`trig_01HZWcyweA9HnX2kLd1CHrfv`) der das Vault liest und ein Debrief erstellt.

**Zustellung:** Push Notification via Claude App (PushNotification Tool).
- Sperrbildschirm: kurze Zusammenfassung (max. 200 Zeichen) mit den 2-3 dringendsten Punkten
- Vollständiges Debrief: sichtbar in claude.ai/code/routines wenn man drauftippt

**Vault-Sync:** Damit der Agent immer den aktuellen Stand liest, Vault-Änderungen regelmäßig pushen:
```bash
cd "/Users/davidglock/Documents/Second Brain/Second Brain"
git add . && git commit -m "Vault update" && git push
```

**Repo:** https://github.com/Davidtsnn/Second-Brain

---

# Vault Context

Dieses Vault ist das Zweites Gehirn von David Glock.

## Über mich

David Glock, 21, Student Online Medien Management (HdM Stuttgart, 4. Semester) und Gründer der Eventagentur BYTC (Best Yet To Come). Seit 15 selbstständig — E-Commerce, Sneaker, YouTube, Dropshipping. Freelancer in Video, Foto und Social Media. Sehr strukturiert, kreativ im Prozess, immer auf persönliche Weiterentwicklung fokussiert. Ausführliches Profil in [[00 Kontext/Über mich]].

## Vault-Struktur

- **00 Kontext/** — Persönliches Profil (Über mich, ICP, Angebot, Schreibstil, Branding). Lies diese Dateien wenn du Content erstellst, Mails schreibst, Angebote formulierst oder in Davids Namen kommunizierst.
- **01 Inbox/** — Brain Dumps, spontane Gedanken, unverarbeitete Notizen. Alles ohne festen Platz landet hier.
- **02 Projekte/** — Aktive Projekte mit konkretem Ziel. Einzelne .md Dateien pro Projekt. Unterordner nur wenn ein Projekt mehrere Dateien braucht.
- **03 Bereiche/** — Laufende Verantwortungsbereiche als Ordner: BYTC, Uni, Sport, Finanzen, Freelancing, Glaube.
- **04 Ressourcen/** — Gesammeltes Wissen nach Themen: Bücher, AI, Social Media Marketing, Eventmanagement.
- **05 Daily Notes/** — Tägliches Logbuch im Format YYYY-MM-DD.md. Gibt Claude Kontinuität zwischen Sessions.
- **06 Archiv/** — Abgeschlossene Projekte und inaktive Bereiche.
- **07 Anhänge/** — Bilder, PDFs, Medien (Obsidian legt hier automatisch ein).

## Schreibregeln

- Keine Gedankenstriche als Satztrenner
- Deutsch als Basis, englische Fachbegriffe werden natürlich eingeflochten

## To Do Liste

- **To Do.md** im Vault-Root ist die Daily To Do Liste — nur Aufgaben für heute oder die nächsten Tage
- Aufgaben mit längeren Deadlines kommen direkt in die jeweilige Projekt- oder Bereichsdatei
- Bei Session-Start Daily To Dos aktualisieren falls nötig

## Regeln für dieses Vault

- Nutze [[Wikilinks]] für Verknüpfungen zwischen Notizen
- Neue Notizen ohne klaren Platz kommen in 01 Inbox/
- Notizen atomar halten: eine Idee pro Notiz wo möglich. Ausnahme: Daily Notes
- Daily Notes im Format: YYYY-MM-DD.md
- YAML Frontmatter nutzen: tags, status (aktiv/abgeschlossen/pausiert), date
- Dateinamen in normaler Schreibweise mit Leerzeichen und Großbuchstaben
- Neue Projekte als einzelne .md Datei direkt in 02 Projekte/ — Unterordner nur wenn nötig
- Bereiche und Ressourcen sind immer Ordner
- Abgeschlossene Projekte nach 06 Archiv/ — nur auf Davids Anweisung, nie eigenständig
- Dateien nicht löschen oder überschreiben ohne Rückfrage
- Wenn David "merk dir das" sagt: Schreibregeln → [[00 Kontext/Schreibstil]], Projekt-Infos → jeweilige Projektdatei, Erkenntnisse → 04 Ressourcen/, Vault-Regeln → diese CLAUDE.md

## Session-Routinen

### Bei Session-Start
Prüfe 01 Inbox/ auf neue Notizen, zeige was drin liegt, und biete an die Einträge in die passenden Ordner einzusortieren.

### Kontext bei Bedarf
Wenn David fragt "Was ist gerade aktuell?", "Wo war ich?" oder ähnliches: Lies die letzten 2-3 Daily Notes in 05 Daily Notes/ und die aktiven Projektdateien in 02 Projekte/ für ein Briefing.

### Bei Session-Ende
Biete an: (1) Daily Note mit Tages-Zusammenfassung erstellen, (2) neue Erkenntnisse als Notizen speichern, (3) Inbox aufräumen falls nötig.
