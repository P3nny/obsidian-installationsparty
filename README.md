# Obsidian Installationsparty

[![Lizenz: CC BY-SA 4.0](https://img.shields.io/badge/Lizenz-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

Schritt für Schritt zum eigenen Second Brain — mit Obsidian, Markdown, Open Knowledge Format und KI-gestützter Wissensorganisation. Workshop-Material für Einsteigerinnen ohne technischen Hintergrund.

## Worum geht's?

Dieses Repository ist das Begleitmaterial zu einer "Obsidian Installationsparty" — einem Workshop, in dem wir gemeinsam ein persönliches, KI-gestütztes Wissenssystem aufbauen: von der Installation von Obsidian über Markdown-Grundlagen bis zu einem Workflow, der unstrukturierte Notizen mithilfe von KI (Claude bzw. GitHub Copilot) in ein strukturiertes Format bringt.

Der Workshop ist Teil eines größeren Vorhabens: Frauen genug Data- und Coding-Literacy zu vermitteln, damit sie die KI-Transformation aktiv mitgestalten können. Dieses Repo ist der erste öffentliche Baustein davon.

## Für wen ist das?

Für alle, die neugierig auf Obsidian, Markdown, Open Knowledge Format und den sinnvollen Einsatz von KI beim Wissensmanagement sind — unabhängig vom technischen Vorwissen. Die Teilnehmerinnen der Installationsparty reichen von "noch nie ein Terminal gesehen" bis Senior-Dev. Das Material ist bewusst so aufgebaut, dass beide Enden dieser Spanne etwas mitnehmen.

Vorausgesetzt wird nichts außer einem eigenen Laptop und Neugier.

## Was du hier lernst

- **Obsidian installieren** und die Grundidee dahinter verstehen
- **Markdown** — die einfache Auszeichnungssprache, mit der alles hier geschrieben ist
- **Vaults** — wie Obsidian deine Notizen organisiert
- **Graph-Ansicht** — wie aus verlinkten Notizen ein sichtbares Wissensnetz wird
- **Sync** — welche Wege es gibt, den Vault auf mehreren Geräten aktuell zu halten
- Installation der KI-Erweiterung **Claudian** samt Claude Code CLI
- Ein **KI-Workflow**, der unstrukturierte Notizen automatisch ins OKF-Format bringt
- Eine Übung, wie du dein Vault als **Second Brain** im Alltag nutzt
- Eine Einordnung: **Vorteile dieses Setups** (Obsidian/Markdown + KI) gegenüber anderen KI-Setups
-  Ein Beispiel für einen **Obsidian-Power-Usecase** (Bases, Canvas, Templates, Cron)
- Open Knowledge Format (OKF)** — ein leichtgewichtiges Format, um Notizen mit Struktur, Herkunft und Vertrauensstatus zu versehen
- **Bonus:** Grundlagen der Command Line — genug, um sich sicher zu bewegen
- **Bonus:** Git-Grundlagen — was es ist, wofür man es braucht, erster Commit und Push mit dem eigenen Vault als Repo

## Format & Ablauf

Der Workshop findet live per Zoom statt, in kleinen Gruppen (3–4 Teilnehmerinnen) mit je einer Coachin an der Seite. Jede arbeitet in ihrem eigenen Tempo entlang der Materialien in diesem Repo. Wer im Termin nicht durchkommt, bekommt einen Nachfolgetermin angeboten.

Auch wenn du nicht live dabei bist: Das Material hier ist so geschrieben, dass es auch im Selbststudium funktioniert.

## So nutzt du dieses Repo

1. Installiere zuerst Obsidian: [obsidian.md](https://obsidian.md)
2. Lade dieses gesamte Repository herunter (`Code` → `Download ZIP`, oder `git clone`, falls du das schon kannst)
3. Öffne den heruntergeladenen Ordner in Obsidian als Vault („Ordner als Vault öffnen")
4. Du findest darin eine vorbereitete Struktur mit Beispielen, Übungen und Referenzmaterial zum Nachschlagen — leg direkt los, oder folge der Reihenfolge der Kapitel
5. Weitere Werkzeuge installierst du erst, wenn du beim jeweiligen Kapitel angekommen bist — die Übersicht dazu steht in `00-vorbereitung/`

## Struktur dieses Repos

```
00-vorbereitung/              Installation, gestaffelt entlang der Kapitel
01-obsidian-und-markdown/     Grundlagen + Markdown-Cheatsheet
02-sync-mehrere-geraete/      Vault auf mehreren Geräten
03-vaults-und-graph-view/     Vaults, Verlinkung, Graph-Ansicht
04-ki-erweiterung/            Claudian-Setup, Workflow zu OKF, Second-Brain-Übung, Vergleich
05-power-usecase/             Bases, Canvas, Templates, Cron
06-okf-format/                Vertiefung Open Knowledge Format (optional)
bonus-command-line/           Command-Line-Grundlagen (freiwillig)
bonus-git/                    Git-Grundlagen + Plugin „Obsidian Git" (freiwillig)
notizen/                      Erklärende Notizen zu Begriffen — zugleich Übungsmaterial
```

Der Ordner `notizen/` ist bewusst kein Kapitel: Dort stehen kurze Notizen zu Begriffen wie Vault, Markdown oder Frontmatter, auf die aus den Kapiteln heraus verlinkt wird. Sie dienen gleichzeitig als Übungsmaterial für Graph-Ansicht, Bases, Canvas und die KI-Übungen — das Material erklärt seine Konzepte also mit genau dem Mittel, um das es geht.

Die Installation in `00-vorbereitung/` ist so aufgeteilt, dass du immer nur das einrichtest, was das nächste Kapitel tatsächlich braucht:

| Teil | Wann | Werkzeug |
| ---- | ---- | -------- |
| A | vor Kapitel 1 | Obsidian, Vault herunterladen und öffnen |
| B | vor Kapitel 4 | Terminal, Claude Code CLI, Claude-Zugang, Claudian |
| C | vor Kapitel 5 | Kern-Plugins prüfen (Bases, Canvas, Templates), optional Cron |
| D | vor Bonus Command Line (optional) | ggf. besseres Windows-Terminal, cowsay, ImageMagick |
| E | vor Bonus Git (optional) | Git, GitHub-Konto, Erweiterung „Obsidian Git" |

Die Kapitel 2, 3 und 6 brauchen nichts zusätzlich.

## Herkunft & Community

Dieser Workshop ist aus dem Kurs ["AI Done Right"](https://www.skool.com/aidoneright) von Barbara Lampl entstanden. Wer nach dem Kurs dranbleiben wollte, hat sich der [Skool-Community](https://www.skool.com/aidoneright) akna "the Gäng"  angeschlossen — aus dieser Community heraus ist diese ehrenamtlich organisierte Session entstanden.

## Über die Organisatorin

Ich baue mittelfristig ein Angebot als Coachin auf, das Frauen die Data- und Coding-Literacy vermittelt, die sie brauchen, um bei der KI-Transformation mitzugestalten statt nur zuzuschauen. Diese Installationsparty ist ein erster Schritt davon — niederschwellig, aber fordernd genug, um wirklich etwas mitzunehmen. [Patricia Ennenbach](https://www.linkedin.com/in/patricia-ennenbach/)

## Lizenz

Dieses gesamte Repository steht unter [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/). Das bedeutet: Du darfst die Inhalte teilen und bearbeiten — auch kommerziell —, musst dabei aber angemessen auf die Quelle verweisen (Namensnennung) und eigene Bearbeitungen unter derselben Lizenz weitergeben (Weitergabe unter gleichen Bedingungen). Den vollständigen Lizenztext findest du in der [LICENSE](./LICENSE)-Datei dieses Repos.

Teile des Command-Line- und Git-Materials orientieren sich am [Django Girls Tutorial](https://github.com/DjangoGirls/tutorial), das ebenfalls unter CC BY-SA 4.0 steht — deshalb ist diese Lizenz für das gesamte Repo gewählt. Übernommene Abschnitte sind entsprechend gekennzeichnet.

**Copyright:** © 2026 [P3nny](https://github.com/P3nny) — Text und Übungen dieses Repos, sofern nicht anders gekennzeichnet.

## Feedback

Fragen, Anmerkungen, Fehler gefunden? Öffne gerne ein Issue in diesem Repo.