# Power-Usecase: Dataview, Canvas, Templates & Cron

## Rahmenerzählung

Stell dir vor, die fünf Notizen aus Kapitel 2 (`Obsidian`, `Zettelkasten`, `Second Brain`, `OKF`, `KI-Workflow`) sind Teil der Wissensbasis einer Solo-Beraterin. Sie nutzt sie, um Konzepte für Kundinnen nachzuschlagen und wiederzuverwenden — will aber auf einen Blick sehen, welche Notizen noch unfertig sind, bevor sie in ein Angebot einfließen.

## Feature 1: Dataview (Hauptübung)

Dataview ist eine Externe Erweiterung, die Notizen nach Frontmatter-Feldern abfragt und als Tabelle oder Liste anzeigt — statt jede Datei einzeln zu öffnen.

**Voraussetzung:** Externe Erweiterung „Dataview" installieren (siehe Kapitel 1, Punkt 6 zu Plugins).

**Übung:**
1. Ergänze bei den 5 Notizen aus Kapitel 2 ein `status`-Feld im Frontmatter (`draft` oder `stable`) — frei nach eigener Einschätzung.
2. Schreibe eine Dataview-Abfrage, die alle Notizen mit `status: draft` auflistet.
3. Erweitere die Abfrage: Liste alle Notizen mit `type` und `status` in einer Tabelle.

**Auflösung:**
```dataview
TABLE type, status
FROM "02-vaults-und-graph-view"
WHERE status = "draft"
```

**Business-Bogen:** Genau so eine Abfrage lässt sich zu einem kleinen Dashboard ausbauen — „Alle Notizen, die vor einem Kundentermin noch geprüft werden müssen" oder „Alle SOPs, die älter als 6 Monate sind" (über `stale_after` aus Kapitel 3). Das ist der Punkt, an dem Obsidian vom reinen Notizzettel zum echten Wissens-Werkzeug wird.

## Feature 2: Canvas

Obsidians eingebautes „unendliches Whiteboard": Notizen, Text-Karten, Bilder oder Web-Links frei auf einer 2D-Fläche platzieren und händisch mit Pfeilen verbinden. Anders als die Graph-Ansicht (automatisch aus Links berechnet) ist Canvas manuell und räumlich — gut für Brainstorming oder um einen Workflow zu skizzieren.

**Mini-Übung:** Lege ein Canvas an, ziehe die fünf Notizen aus Kapitel 2 als Karten hinein und ergänze eine Freitext-Karte mit einem Kommentar — z. B. so, wie du das eigene Wissenssystem einer Kundin präsentieren würdest.

## Feature 3: Templates

Zwei Ebenen: Die **Obsidian-Erweiterung „Templates"** fügt einen fest vordefinierten Textbaustein in eine neue Notiz ein (z. B. das OKF-Frontmatter-Gerüst aus Kapitel 3 direkt fertig mit `type:`, `status:`, `sources:`). Die **Externe Erweiterung „Templater"** kann zusätzlich dynamische Werte einsetzen (heutiges Datum, Cursor-Position, kleine Skripte).

**Mini-Übung:** Lege ein Template namens `Neues Konzept.md` an, das die OKF-Pflichtfelder leer vorgibt. Erzeuge daraus eine neue Notiz.

## Feature 4 (Ausblick, ohne Übung): Cron

Es gibt eine Externe Erweiterung namens **„Cron"** (`obsidian-cron`), das Obsidian-Befehle oder eigene Skripte nach echter Cron-Syntax zeitgesteuert ausführt — solange Obsidian offen bzw. im Hintergrund läuft. Alternative, falls Obsidian geschlossen ist: ein systemseitiger Cron-Job (z. B. via Task Scheduler/`cron`), der ein Skript anstößt, das Dateien im Vault verändert.

**Business-Beispiel:** Ein wöchentlicher Job, der alle Notizen mit abgelaufenem `stale_after` (aus Kapitel 3) findet und automatisch auf `status: draft` zurücksetzt oder eine Erinnerungs-Notiz erzeugt — „diese SOPs müssen überprüft werden."

## Exkurs: Was ist eine SOP

**SOP** = Standard Operating Procedure, „Standardarbeitsanweisung": eine feste, dokumentierte Schritt-für-Schritt-Anleitung für einen wiederkehrenden Ablauf — z. B. „So läuft ein Erstgespräch mit einer neuen Kundin ab". Für Solo-Selbstständige sind SOPs typischerweise selbst Notizen im Vault, oft mit `type: SOP` im OKF-Frontmatter — und genau da wird `stale_after` praktisch.

### Links
https://www.mathoi.at/2023/03/25/obsidian-plugins-im-produktiveinsatz/
https://www.mathoi.at/2024/01/30/obsidian-plugins-ein-paar-gedanken/