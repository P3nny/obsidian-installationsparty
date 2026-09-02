# Obsidian auf mehreren Geräten synchronisieren

Dein Vault ist bisher nur auf einem Rechner. Wenn du auch am Handy oder einem zweiten Rechner darauf zugreifen willst, brauchst du eine Sync-Lösung. Drei Wege, sortiert von einfach nach anspruchsvoll:

## Option 1: Obsidian Sync (offizieller Dienst)

Der von den Obsidian-Entwicklern selbst angebotene Sync-Dienst.

**Einrichtung:** Einstellungen → **Sync** → Konto erstellen/einloggen → Vault auswählen → Sync aktivieren. Auf dem zweiten Gerät: Obsidian installieren, mit demselben Konto einloggen, Vault aus der Liste auswählen.

| Vorteile | Nachteile |
|---|---|
| Am einfachsten einzurichten, wenige Klicks | Kostenpflichtig (Abo) |
| Von den Obsidian-Machern selbst betrieben, gut getestet | Zusätzliche Kosten neben einem eventuellen Claude-Abo |
| Versionsverlauf inklusive | — |

## Option 2: iCloud / Google Drive / OneDrive

Deinen Vault-Ordner einfach in einen bereits vorhandenen Cloud-Ordner legen (oder verschieben), den du ohnehin schon nutzt.

**Einrichtung:** Vault-Ordner in den lokalen Sync-Ordner deines Cloud-Anbieters verschieben (z. B. `iCloud Drive/Obsidian/` oder `Google Drive/Obsidian/`), dann in Obsidian über „Open folder as vault" von dort aus öffnen — auf jedem Gerät, auf dem derselbe Cloud-Ordner eingerichtet ist.

| Vorteile | Nachteile |
|---|---|
| Kostenlos, falls du den Speicherplatz ohnehin schon hast | Gelegentlich Konflikte, wenn du auf zwei Geräten gleichzeitig dieselbe Notiz bearbeitest |
| Kein zusätzlicher Dienst nötig | Kein Obsidian-eigener Versionsverlauf |

## Option 3: Git

Dein Vault ist technisch gesehen sowieso schon ein Git-Repository — genau wie das Workshop-Repo, das du in der Vorbereitung heruntergeladen hast. Damit lässt sich derselbe Mechanismus auch für den eigenen, wachsenden Vault nutzen: Änderungen committen, auf ein Remote-Repository pushen, auf dem zweiten Gerät pullen.

**Vorteile:** kostenlos, vollständiger Versionsverlauf jeder einzelnen Änderung, keine Abhängigkeit von einem bestimmten Cloud-Anbieter.

**Nachteil:** technisch anspruchsvoller als die beiden Optionen oben — du musst Git-Grundbefehle kennen (`commit`, `push`, `pull`) und mit Merge-Konflikten umgehen können, falls doch mal zwei Geräte gleichzeitig etwas ändern.

**Voraussetzung in jedem Fall:** Grundkenntnisse der Command Line — Git wird über das Terminal bedient. Mehr dazu im Bonus-Kapitel Command Line, danach im Bonus-Kapitel Git, wo genau dieser Workflow Schritt für Schritt erklärt wird.

---

**Kurzempfehlung:** Für den Einstieg reicht Option 1 oder 2 völlig aus. Option 3 lohnt sich vor allem für alle, die sowieso vorhaben, sich mit Command Line und Git zu beschäftigen — dann bekommt man Sync quasi kostenlos obendrauf.
