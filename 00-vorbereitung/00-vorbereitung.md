# 00 – Vorbereitung

## Worum geht's in diesem Kapitel?

Bevor es mit Markdown, dem Open Knowledge Format oder KI-Workflows losgeht, brauchst du zwei Dinge:

1. **Obsidian** auf deinem Rechner installiert
2. Das **Workshop-Vault** von GitHub heruntergeladen und in Obsidian geöffnet

Danach hast du alle weiteren Kapitel bereits vor dir liegen — direkt im Vault, als Notizen, die du nach und nach durcharbeitest.

## Schritt 1: Obsidian installieren

- Rufe [obsidian.md](https://obsidian.md) auf
- Lade die passende Version für dein Betriebssystem herunter (Windows / Mac / Linux)
- Installiere Obsidian wie gewohnt
- Öffne Obsidian einmal — du kannst den Startdialog erstmal ignorieren, wir brauchen gleich einen eigenen Ordner

## Schritt 2: Das Vault von GitHub herunterladen

Das komplette Workshop-Material liegt in diesem Repo:
`https://github.com/P3nny/obsidian-installationsparty`

So kommst du an die Dateien:

1. Öffne das Repo im Browser
2. Klicke auf den grünen Button `Code`
3. Wähle `Download ZIP`
4. Entpacke die ZIP-Datei an einem Ort, den du wiederfindest (z. B. Desktop oder Dokumente)

*(Wer Git schon kennt, kann alternativ `git clone` benutzen — mehr dazu im Bonus-Kapitel Git.)*

## Schritt 3: Vault in Obsidian öffnen

1. In Obsidian: **„Open folder as vault"**
2. Wähle den entpackten Ordner aus
3. Obsidian öffnet den Ordner als Vault — du siehst links die Dateistruktur mit allen Kapiteln

Im Vault liegen außerdem schon fünf vorbereitete Beispiel-Notizen (`Obsidian.md`, `Zettelkasten.md`, `Second Brain.md`, `OKF.md`, `KI-Workflow.md`) mit fertigem Inhalt, aber noch **ohne Verlinkung**. Die brauchst du erst in Kapitel 2 — für jetzt reicht es, wenn du weißt, dass sie schon da sind.

## Schritt 4: Community Plugins installieren

Für den Power-Usecase in Kapitel 4 brauchst du drei zusätzliche Plugins. Die installierst du am besten schon jetzt, damit später keine Zeit für Setup drauf geht.

*Hinweis: Obsidian ist standardmäßig auf Deutsch — die folgenden Bezeichnungen entsprechen der deutschen Version.*

1. Öffne die **Einstellungen** (Zahnrad-Symbol unten links)
2. Gehe zu **Externe Erweiterungen** (das ist die deutsche Bezeichnung für „Community plugins")
3. Falls der **eingeschränkte Modus** noch aktiv ist: einmal auf **Eingeschränkten Modus deaktivieren** klicken (Bestätigung akzeptieren)
4. Klicke auf **Durchsuchen**, suche nach jedem der folgenden Plugins, klicke jeweils auf **Installieren** und danach auf **Aktivieren**:

| Plugin | Wofür (Kapitel 4) |
|---|---|
| **Dataview** | Notizen nach Frontmatter-Feldern abfragen (Hauptübung) |
| **Templater** | Dynamische Templates mit dem OKF-Frontmatter-Gerüst |
| **Cron** | Zeitgesteuerte Automatisierung (Ausblick, ohne Pflichtübung) |

*Canvas und das eingebaute Plugin „Templates" (unter **Obsidian-Erweiterungen**) brauchen keine Installation — die sind schon in Obsidian dabei, ggf. nur unter Einstellungen → Obsidian-Erweiterungen zu aktivieren.*

Ab hier liegt die gesamte weitere Struktur bereits vor dir:

```
00-vorbereitung/
01-obsidian-und-markdown/
02-vaults-und-graph-view/
03-okf-format/
04-power-usecase/
05-command-line/
06-ki-erweiterung/
07-workflow-notizen-zu-okf/
08-second-brain-uebung/
09-vergleich-ki-setups/
bonus-git/
```

## Offene Punkte / noch zu ergänzen

- [ ] Screenshots für Download-Button und „Open folder as vault"
- [ ] Hinweise für typische Stolperfallen (z. B. Sicherheitswarnung beim ersten Öffnen, falsche ZIP-Entpackung)
- [ ] Kurzer Check am Ende: „Siehst du die Ordnerstruktur links? Dann ist alles bereit."
- [ ] Sicherstellen, dass die 5 Beispiel-Notizen im tatsächlichen Vault-Download enthalten sind
- [ ] Screenshot für Community-Plugin-Suche/Installation
