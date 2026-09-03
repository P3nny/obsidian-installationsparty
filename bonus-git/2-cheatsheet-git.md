# Git Cheatsheet

Reine Referenz zum Nachschlagen — keine Übung. Deckt die Befehle ab, die im Bonus-Kapitel [[1-git|Git]] vorkommen, plus ein paar weitere für den Alltag.

| Was | Befehl | Wozu |
|---|---|---|
| Einmalig einrichten | `git config --global user.name "Name"` | Name für jeden Commit hinterlegen |
| | `git config --global user.email "mail"` | E-Mail für jeden Commit hinterlegen |
| Repository anlegen | `git init` | aus dem aktuellen Ordner ein Repository machen |
| | `git clone URL` | ein bestehendes Repository herunterladen |
| Status & Verlauf | `git status` | was ist geändert, aber noch nicht gespeichert? |
| | `git log` | alle bisherigen Speicherpunkte ansehen |
| | `git diff` | zeilengenau zeigen, was sich geändert hat |
| Speichern | `git add .` | alle Änderungen für den nächsten Commit vormerken |
| | `git add datei.md` | nur eine bestimmte Datei vormerken |
| | `git commit -m "Notiz"` | Speicherpunkt mit Beschreibung anlegen |
| Hochladen/Herunterladen | `git push` | eigene Speicherpunkte zu GitHub hochladen |
| | `git pull` | Speicherpunkte von GitHub herunterladen |
| | `git remote add origin URL` | GitHub-Adresse einmalig hinterlegen |
| Zurückholen | `git restore datei.md` | letzte gespeicherte Version einer Datei wiederherstellen |
| | `git restore --staged datei.md` | Datei aus der Vormerkung nehmen, Änderung bleibt erhalten |
| Zweige (fortgeschritten) | `git branch` | alle Zweige auflisten |
| | `git branch -M main` | aktuellen Zweig in `main` umbenennen |
| | `git checkout -b name` | neuen Zweig anlegen und wechseln |

## Weiterführend

Für alles darüber hinaus (Merge-Konflikte, Rebasing, Tags, Zusammenarbeit im Team):

- [docs.github.com – Git-Cheatsheet](https://docs.github.com/en/get-started/git-basics/git-cheatsheet) — offizielle, mehrsprachige Referenz von GitHub, wird laufend gepflegt
- [GitHub Education – Git-Cheatsheet als PDF](https://education.github.com/git-cheat-sheet-education.pdf) — kompakt zum Ausdrucken oder offline nutzen

Zurück zum Kapitel: [[1-git|Bonus: Git]].
