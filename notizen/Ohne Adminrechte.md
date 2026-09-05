---
type: Konzept
---

Firmenrechner erlauben oft keine Installationen, die Systemdateien oder die Registry anfassen. Für diesen Workshop ist das fast nie ein Problem: Die meisten Werkzeuge hier installieren entweder direkt ins eigene Benutzerprofil (kein Admin nötig) oder gibt es als **portable Version** — ein Programm, das ganz ohne Installation aus einem entpackten Ordner heraus läuft.

| Werkzeug                             | Normalfall                                                                   | Ohne Adminrechte                                                                                                                                           |
| ------------------------------------ | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Claude Code CLI                      | —                                                                            | installiert ohnehin nur ins eigene Benutzerprofil, nie Adminrechte nötig                                                                                   |
| PATH-Eintrag korrigieren             | —                                                                            | „Umgebungsvariablen für dieses Konto bearbeiten" statt der systemweiten Variante — geht ohne Adminrechte                                                   |
| Besseres Windows-Terminal (Git Bash) | [Git for Windows](https://git-scm.com/downloads)                             | entfällt: bleib bei PowerShell — das Bonus-Kapitel Command Line gibt zu jedem Unix-Befehl eine PowerShell-Alternative                                      |
| Obsidian Web Clipper                 | Browser-Erweiterung installieren                                             | sperrt die IT auch das: die zwei fertigen Beispiel-Clips in `Clippings/` decken alle Übungen ab                                                            |
| `cowsay` (Bonus Command Line)        | `brew`/`apt install cowsay`                                                  | PowerShell-Modul: `Install-Module -Name CowsaySharp -Scope CurrentUser`, danach `Get-Cowsay -message "Text"`                                              |
| ImageMagick (Bonus Command Line)     | Installer von [imagemagick.org](https://imagemagick.org/script/download.php) | [portable ZIP-Version](https://imagemagick.org/script/download.php#windows) entpacken — `convert.exe` läuft direkt aus dem Ordner                          |
| Git (Bonus-Kapitel Git)              | [Git for Windows](https://git-scm.com/downloads)                             | [PortableGit](https://git-scm.com/install/windows) („Thumbdrive Edition", 7z-Archiv unter „Other Git for Windows downloads") — entpacken, kein Setup nötig |

**Faustregel:** Blockt die IT sogar das noch, ist keine der Übungen in diesem Workshop zwingend darauf angewiesen — Bonus-Kapitel bleiben freiwillig, und für Kernkapitel gibt es an jeder Stelle einen Ausweg (z. B. die Beispiel-Clips statt Web Clipper). Im Zweifel: IT fragen oder in der Session eine Coachin ansprechen.
