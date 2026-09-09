---
type: Konzept
---

Eine Liste von Ordnern, in denen dein [[Terminal]] nach Programmen sucht, wenn du einen Befehl tippst. Tippst du `claude`, schaut das Terminal ausschließlich in diesen Ordnern nach — nirgendwo sonst.

Ein Installer trägt seinen Programm-Ordner normalerweise selbst dort ein. Zwei Dinge gehen dabei häufig schief:

- **Ein bereits offenes Terminal-Fenster liest die PATH-Liste nicht neu ein.** Lösung: Fenster komplett schließen, neues öffnen.
- **Der Installer trägt den Ordner gar nicht zuverlässig ein** — kommt in der Praxis öfter vor, als man denkt. Dann bleibt nur: von Hand ergänzen (Windows: Umgebungsvariablen-Einstellungen; Mac/Linux: Zeile in `~/.zshrc`/`~/.bash_profile`/`~/.bashrc` anhängen).

Betrifft nicht nur Claude Code — genau dasselbe Muster taucht bei jedem kommandozeilenbasierten Tool auf, das „installiert, aber nicht gefunden" wird.
