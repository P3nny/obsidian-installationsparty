# Projekt: Obsidian-Installationsparty (Workshop-Material)

## Worum geht's

Live-Workshop (Zoom + Breakout-Rooms) für eine technisch heterogene, überwiegend Einsteigerinnen-Gruppe. Ziel: Obsidian + KI-Second-Brain in Aktion erleben. Materialien liegen als Markdown-Dateien in diesem Vault/Repo, angelehnt ans Django-Girls-Tutorial.

## Aktuelle Struktur (Stand: siehe Ordner)

```
00-installation.md      (im Root, nicht in einem Kapitel-Ordner) Gestaffelt entlang der Kapitel-Ordner: A=Obsidian+Vault (vor Kap. 1), B=Terminal/Claude-Code-CLI/Claudian (vor Kap. 4), C=Kern-Plugins prüfen + optional Cron (vor Kap. 5), D=Command-Line-Werkzeuge (optional), E=Git (optional)
01-obsidian-und-markdown/
02-sync-mehrere-geraete/
03-vaults-und-graph-view/
04-ki-second-brain/         (5 Teile: Plugin-Setup&Chat, Wissen-reinholen/Web-Clipper, Verdichten&Wiederfinden, Eigenes-Wissen, OKF)
bonus-power-usecases-obsidian/ (Bonus, kein Pflichtkapitel: Templates, Automatisierungs-Ausblick, Cron, kurz Bases/Canvas)
bonus-command-line/         (Pull-Marketing aus Kapitel 4, kein Pflichtkapitel)
notizen/                    Konzept-/Begriffsnotizen, dienen zugleich als Demo-Material (Graph-Ansicht, Bases, Canvas, KI-Übungen)
Clippings/                  Beispiel-Clips des Web Clippers, Rohmaterial für Kapitel 4 Teil 2/3
bonus-git/                  Git-Grundlagen + Plugin „Obsidian Git"
```

**Wichtig bei Strukturänderungen:** Kapitel-Nummern werden im Fließtext quervermerkt („siehe Kapitel 3" etc.) — bei Umbenennung/Umsortierung IMMER per `grep -rn "Kapitel [0-9]"` alle Dateien durchsuchen und Referenzen mitziehen.

## Tokensparend arbeiten

Jede Änderung soll so wenig Tokens wie möglich kosten — beim Schreiben *und* bei allen künftigen Änderungen.

- **Eine Information gehört an genau eine Stelle.** Vor dem Schreiben prüfen: Steht das schon irgendwo? Wenn ja, dorthin verlinken statt wiederholen. Was an drei Stellen steht, muss später dreimal geändert werden — und wird garantiert irgendwo vergessen.
- **Verweise statt Kopien.** Das Konzept in die Begriffsnotiz (`notizen/`), das Kapitel verlinkt nur `[[Begriff]]`. Installationsschritte gehören ausschließlich in `00-installation.md`; Kapitel verweisen auf „Teil B, Schritt 7b" statt die Anleitung zu wiederholen.
- **Beim Ändern nur den betroffenen Absatz anfassen**, nicht ganze Dateien neu schreiben. Gezielte Edits statt Komplett-Neufassungen.
- **Vorsicht bei Redundanz-Fallen** in diesem Repo: Kapitelstruktur steht in `README.md`, `CLAUDE.md` und der Tabelle in `00-installation.md`; Werkzeug-Listen in `README.md` und `00-installation.md`. Beim Umbauen alle drei prüfen — oder besser: nicht noch eine vierte Stelle schaffen.
- **Erst lesen, was nötig ist.** Gezielt greppen statt ganze Ordner einlesen.

## Werkzeug-Entscheidungen (aktueller Stand)

- **Claudian** ist das einzige KI-Plugin, das genutzt wird — kein Ollama, kein Copilot-Plugin, kein Dataview (alles bewusst rausgeworfen nach Praxistests)
- **Obsidian Web Clipper** (offizielle Browser-Erweiterung) als optionaler Install in Teil B, Schritt 7b. Bewusst optional: Firmenrechner erlauben oft nur freigegebene Erweiterungen. Fallback sind die zwei fertigen Clips in `Clippings/`, mit denen alle Übungen funktionieren.
- Inhaltliche Grundlage für den Second-Brain-Kreislauf sind die zwei Clippings (Karpathy: ingest → compile → Q&A → zurückfilen → linting; Tom Liu: der Engpass ist die Fleißarbeit nach dem Lesen).
- Claude Code CLI wird über den **nativen Installer** eingerichtet (kein Node.js/npm nötig): `curl -fsSL https://claude.ai/install.sh | bash` (Mac/Linux) bzw. `irm https://claude.ai/install.ps1 | iex` (Windows).
- **Bases** (nativ, kein Plugin) statt Dataview für Datenbank-Ansichten.
- **Templates** (natives Kern-Plugin) statt Templater — die Übungen brauchen nur feste Bausteine und `{{date}}`/`{{title}}`/`{{time}}`. Templater steht im Bonus-Kapitel Power-Usecase nur noch als Ausblick.
- Claude Code CLI läuft auch in **cmd** (eigener Installer `install.cmd`), nicht nur in PowerShell — Windows-Teilnehmerinnen sind also nie blockiert.
- Free-Tarif von claude.ai reicht NICHT für Claude Code/Claudian — nur Pro/Max-Abo oder API-Key.

## Hausstil für Kapitel-Dateien

- Muster: kurzer **Kontext** → **Übung** → wo sinnvoll **Auflösung/Erwartung** inline (nicht immer gesammelt am Ende).
- **Kurz halten.** So viel wie nötig, so wenig wie möglich. Übersichtstabellen statt Fließtext, wo es passt.
- Deutsche Obsidian-UI-Begriffe durchgängig verwenden (Einstellungen, Externe Erweiterungen, Seitenleiste, Befehlspalette, Graph-Ansicht, Rückverweise — nicht die englischen Originalbegriffe).
- Fachbegriffe (z. B. „Frontmatter") möglichst als eigene, verlinkte Beispiel-Notiz im Vault erklären (`[[Begriff]]`), nicht nur im Fließtext — das demonstriert das Prinzip gleich mit.
- Konzepte möglichst dort einführen, wo sie zum ersten Mal praktisch gebraucht werden, nicht vorab abstrakt.
- Am Ende jeder Kapiteldatei kurz verweisen, was als Nächstes kommt.

## Zielgruppe im Hinterkopf behalten

- Komplette Einsteigerinnen bis Senior-Devs, aber Umfrage-Rückmeldungen zeigen: eher wenig Vorerfahrung, oft ohne Adminrechte (Firmenrechner), Windows-Mehrheit.
- Vor jedem technischen Schritt fragen: „Geht das ohne Adminrechte? Was, wenn nicht?"
- Terminal-Nutzung wird nicht als Pflicht verkauft, sondern als Pull-Marketing über einen Aha-Moment im KI-Kapitel angeboten (Bonus-Kapitel Command Line).

## Copyright/Quellen

Bei externen Quellen (Blogposts, Doku): paraphrasieren, nicht wörtlich übernehmen, Quelle per Fußnote nennen.

## Offene Punkte (siehe auch „Offene Punkte"-Listen in den einzelnen Dateien)

- `bonus-git/1-git.md` ausgearbeitet (Videospiel-Speicherpunkt-Analogie, eigenes Repo, Auth über Git Credential Manager / `gh`, PAT nur als Notfall, danach Plugin „Obsidian Git"). Offene Punkte stehen in der Datei.
- Diverse Screenshots/GIFs noch nicht erstellt (in `00-installation.md` gelistet).
- Zeitbudget für Teil A der Installation nur grob geschätzt, nicht live getestet.
- Frontmatter-Verlinkung als Pilot eingeführt — bei Bedarf auf weitere Begriffe ausweiten (z. B. Vault, Terminal, Agentische KI als eigene Konzept-Notizen).
