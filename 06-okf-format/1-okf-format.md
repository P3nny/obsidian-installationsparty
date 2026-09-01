# OKF – Open Knowledge Format

*Du hast das OKF-Frontmatter (`type`, `status`, `sources` ...) in Kapitel 5 schon in Aktion gesehen — deine KI hat damit gearbeitet, ohne dass du wissen musstest, was genau dahintersteckt. Dieses Kapitel ist die Vertiefung für alle, die es jetzt genauer wissen wollen. Kein Muss, um mit dem Workshop fertig zu sein — aber ein spannender Blick unter die Haube.*

Basiert auf der offiziellen Spezifikation von Google: [github.com/GoogleCloudPlatform/knowledge-catalog](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md). Für diesen Workshop reicht ein vereinfachter Ausschnitt der Kernfelder.

## Was ist OKF

OKF ist ursprünglich für Datenmanagement in Unternehmen gedacht: eine Konvention aus Markdown-Datei + YAML-Frontmatter, die sagt, woher eine Notiz stammt, wie sehr man ihr vertrauen kann und ob sie noch aktuell ist.

## Kernfelder

- **`type`** — welche Art Notiz ist das (einzige Pflichtangabe)
- **`sources`** — woher stammt die Information (Provenienz)
- **`generated` / `verified`** — wer/was hat es erstellt, wer hat es bestätigt (Vertrauens-Stufen: unverified / machine-confirmed / human-reviewed)
- **`status`** — draft / stable / deprecated
- **`stale_after`** — ab wann gilt der Inhalt als veraltet

## Nutzen über Datenmanagement hinaus

### Wissenschaftliches Arbeiten
- `sources` mit Fußnoten-Verknüpfung ist im Kern ein Zitations-System
- `verified` unterscheidet eine ungeprüfte Idee von einer bereits gegengelesenen Aussage
- `status: draft/stable` macht sichtbar, welche Notizen noch Rohmaterial sind und welche belastbar zitierfähig sind
- `stale_after` ist relevant für Forschung mit sich verändernden Grundlagen (z. B. Studienlage)
- Markdown + Git schenkt eine Versionsgeschichte der eigenen Gedankenentwicklung

### Solo-Selbstständige
- `sources` mit `author`/`last_modified` hält fest, woher Kundenwissen oder Marktrecherchen stammen — nachvollziehbar auch Monate später
- `status` unterscheidet aktuelle SOPs/Vorlagen von veralteten
- `generated`/`verified` schafft Klarheit: War das ein KI-Entwurf, oder von mir selbst geprüft, bevor es an eine Kundin ging?
- Die eigene Notizsammlung wird KI-lesbar und -durchsuchbar, ohne dass man ein zusätzliches Tool braucht

## Wofür OKF NICHT gedacht ist

Für ein tägliches Journal oder simple Aufgabenverwaltung wäre OKF überdimensioniert. Niemand will bei jedem Tageseintrag Felder wie `sources` oder `verified` pflegen; dafür reichen einfache Tags oder spezialisierte Plugins (z. B. „Tasks").

Die Unterscheidung passt zum Zettelkasten-Prinzip aus Kapitel 1: Luhmann trennte zwischen *flüchtigen Notizen* (schnell, unstrukturiert — euer Journal) und *permanenten Notizen* (durchdacht, verknüpft, dauerhaft). OKF ist ein Format für die **permanenten** Notizen — die, die es wert sind, dauerhaft im Second Brain zu bleiben.

Praktisch heißt das: Man schreibt frei im Journal, und nur wenn eine Idee es wert ist, bekommt sie beim „Befördern" ins Second Brain einen `type`, vielleicht `status: draft`, später `verified`. Genau diesen Übergang — von unstrukturierter Notiz zu OKF-Format — behandelt Kapitel 5 im Detail.
