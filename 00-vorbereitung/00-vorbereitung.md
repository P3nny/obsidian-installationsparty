# 00 – Vorbereitung

## Worum geht's in diesem Kapitel?

Du installierst nicht alles auf einmal, sondern immer genau das, was das nächste Kapitel braucht. Für den Start reichen zwei Dinge:

1. **Obsidian** auf deinem Rechner installiert
2. Das **Workshop-Vault** von GitHub heruntergeladen und in Obsidian geöffnet

Danach liegen alle weiteren Kapitel bereits im Vault vor dir. Die restlichen Werkzeuge holst du dir erst, wenn du beim jeweiligen Kapitel angekommen bist.

## Was wird wann gebraucht?

| Kapitel                          | Werkzeug                                                        | Vorbereitung |
| -------------------------------- | --------------------------------------------------------------- | ------------ |
| `01-obsidian-und-markdown/`      | Obsidian + Vault                                                  | **Teil A**   |
| `02-sync-mehrere-geraete/`       | nichts — hier wird nur verglichen und entschieden                 | —            |
| `03-vaults-und-graph-view/`      | nichts — alles schon in Obsidian eingebaut                        | —            |
| `04-ki-erweiterung/`             | Terminal, Claude Code CLI, Claude-Zugang, Claudian                | **Teil B**   |
| `05-power-usecase/`              | Bases, Canvas, Templates (alle nativ) — optional Cron              | **Teil C**   |
| `06-okf-format/`                 | nichts — reine Vertiefung                                         | —            |
| `bonus-command-line/` (optional) | ggf. besseres Windows-Terminal, cowsay, ImageMagick               | **Teil D**   |
| `bonus-git/` (optional)          | Git                                                               | **Teil E**   |

Nur **Teil A** ist Pflicht, bevor es losgeht. Alles andere kommt zum passenden Zeitpunkt in der Session.

---

# Teil A: Basis — vor Kapitel 1

## Schritt 1: Obsidian installieren

- Rufe die Webseite [obsidian.md](https://obsidian.md) auf
- Lade die passende Version für dein Betriebssystem herunter (Windows / Mac / Linux)
- Installiere Obsidian wie gewohnt
- Öffne Obsidian einmal — den Startdialog kannst du erstmal ignorieren, wir brauchen gleich einen eigenen Ordner

## Schritt 2: Das Vault von GitHub herunterladen

Das komplette Workshop-Material liegt in diesem Repo:
https://github.com/P3nny/obsidian-installationsparty

So kommst du an die Dateien:

1. Öffne das Repo im Browser
2. Klicke auf den grünen Button `Code`
3. Wähle `Download ZIP`
4. Entpacke die ZIP-Datei an einem Ort, an dem Du damit arbeiten möchtest

*(Wer Git schon kennt, kann `git clone` benutzen — mehr dazu im Bonus-Kapitel Git.)*

## Schritt 3: Vault in Obsidian öffnen

1. In Obsidian: **„Ordner als Vault öffnen"**
2. Wähle den entpackten Ordner aus
3. Obsidian öffnet den Ordner als Vault — du siehst links die Dateistruktur mit allen Kapiteln

Damit ist Teil A abgeschlossen. Die Kapitel 1 bis 3 brauchen nichts weiter als Obsidian selbst — leg direkt los.

---

# Teil B: Vor Kapitel 4 (KI-Erweiterung)

In Kapitel 4 steuerst du Claude direkt aus Obsidian heraus. Dafür brauchst du drei Bausteine: ein Terminal, die Claude Code CLI und das Obsidian-Plugin Claudian.

Damit begegnet dir hier zum ersten Mal das **Terminal** — das Fenster mit dem blinkenden Cursor, in das man Befehle tippt. Dass das im ersten Moment einschüchternd wirkt, geht fast allen so. Tatsächlich ist es nur eine andere Art, dem Rechner zu sagen, was er tun soll: tippen statt klicken. Auswendig lernen musst du nichts, jeden Befehl findest du hier zum Kopieren — und wer sich später darauf einlässt, hat damit erstaunlich schnell ein Werkzeug in der Hand, das er nicht mehr hergeben will (mehr dazu im Bonus-Kapitel Command Line).

## Schritt 4: Terminal finden (nur Windows)

*Mac- und Linux-Nutzerinnen haben mit dem eingebauten Terminal schon alles, was sie brauchen, und können diesen Schritt überspringen.*

Windows hat nicht nur ein Terminal, sondern mehrere — mit unterschiedlichen Fähigkeiten. Für Kapitel 4 reicht ein kurzer Check, welches du hast:

1. Drücke die Windows-Taste und tippe **„Terminal"**. Erscheint eine App namens **Terminal** mit einem bunten Symbol? → Du hast **Windows Terminal**, die modernste Variante (bei Windows 11 meist vorinstalliert).
2. Falls nicht: Tippe stattdessen **„PowerShell"**. Erscheint **Windows PowerShell**? → Zweitbeste Option, auf praktisch jedem Windows-Rechner vorinstalliert.
3. Falls auch das nicht auftaucht: Tippe **„cmd"** oder **„Eingabeaufforderung"** — die gibt es garantiert.

- Steht am Zeilenanfang `PS C:\Users\DeinName>` → **PowerShell** (auch innerhalb von Windows Terminal)
- Steht dort `C:\Users\DeinName>` ohne das `PS` → **cmd / Eingabeaufforderung**

*Und wenn ich gar nichts davon finde?* Das kommt praktisch nicht vor — Claude Code setzt Windows 10 (Version 1809) oder neuer voraus, und dort ist mindestens die Eingabeaufforderung immer installiert. Findet die Suche nichts, liegt es meist an der Windows-Suche selbst: Drücke dann `Windows-Taste + R`, tippe `cmd` und drücke Enter. Blockt die IT deines Firmenrechners tatsächlich beide Terminals, gibt es einen Ausweg ganz ohne Kommandozeile — siehe den Kasten am Ende von Schritt 5.

## Schritt 5: Claude Code CLI installieren

Das ist das Werkzeug, mit dem Claudian (Schritt 7) Claude tatsächlich steuert. Ein einziger Copy-Paste-Befehl, offizielle Software von Anthropic — kein Adminrecht nötig. Nimm die Zeile, die zu deinem Terminal aus Schritt 4 passt:

| Dein Terminal              | Befehl                                                                    |
| -------------------------- | ------------------------------------------------------------------------- |
| macOS / Linux              | `curl -fsSL https://claude.ai/install.sh \| bash`                          |
| Windows **PowerShell**     | `irm https://claude.ai/install.ps1 \| iex`                                 |
| Windows **Eingabeaufforderung (cmd)** | `curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd` |

Test, ob's geklappt hat: `claude --version` sollte eine Versionsnummer zeigen.

**Wenn eine Fehlermeldung kommt:**

- `'irm' wird nicht als Befehl erkannt` → Du bist in cmd, hast aber den PowerShell-Befehl genommen. Nimm die cmd-Zeile.
- `Die Token "&&" ist kein gültiges Anweisungstrennzeichen` → Umgekehrt: Du bist in PowerShell und hast die cmd-Zeile genommen.
- Etwas mit **„Execution Policy"** → Eine Sicherheitseinstellung mancher Firmenrechner, die PowerShell-Skripte blockiert. Probier in diesem Fall die cmd-Zeile; hilft das nicht, bei der IT nachfragen oder in der Session eine Coachin fragen.

*Optional für Windows: Wenn du [Git for Windows](https://git-scm.com/downloads/win) installiert hast, nutzt Claude Code dessen Git Bash und kann Befehle etwas komfortabler ausführen — ohne läuft alles über PowerShell. Nötig ist das nicht, und du kannst es jederzeit nachholen. Wer das optionale Bonus-Kapitel Command Line oder Git machen will, installiert es dort ohnehin (Teil D bzw. E).*

*Notausgang ohne Terminal: Blockt die IT beide Terminals komplett, gibt es die **Claude Desktop App** ([claude.com/download](https://claude.com/download)) — dieselbe Technik, aber mit grafischer Oberfläche statt Kommandozeile. Sie setzt allerdings ein Pro- oder Max-Abo voraus (kein API-Key) und läuft außerhalb von Obsidian, du kannst die Übungen aus Kapitel 4 damit also nur teilweise nachvollziehen. Sag in der Session Bescheid, wenn du in diesem Fall bist.*

## Schritt 6: Bei Claude anmelden

**Falls du ein Claude Pro- oder Max-Abo hast:** Tippe `claude` ins Terminal, es öffnet sich dein Browser für den Login. Die Nutzung läuft über dein bestehendes Abo, keine Zusatzkosten.

**Falls du kein Abo hast (auch der kostenlose Free-Tarif reicht hier nicht aus):** Du brauchst einen API-Key.

1. **console.anthropic.com** öffnen, registrieren
2. Unter **Billing** eine Zahlungsmethode hinterlegen, Guthaben aufladen (5 $ reichen zum Start)
3. Unter **API Keys** → **Create Key**, Namen vergeben, Key **sofort kopieren** (wird nur einmal angezeigt, beginnt mit `sk-ant-api03-…`)
4. `claude` im Terminal starten, den Key dort einfügen, wenn danach gefragt wird

## Schritt 7: Claudian in Obsidian installieren

*Hinweis: Obsidian ist standardmäßig auf Deutsch — die folgenden Bezeichnungen entsprechen der deutschen Version.*

1. Öffne die **Einstellungen** (Zahnrad-Symbol unten links)
2. Gehe zu **Externe Erweiterungen** (das ist die deutsche Bezeichnung für „Community plugins")
3. Falls der **eingeschränkte Modus** noch aktiv ist: einmal auf **Eingeschränkten Modus deaktivieren** klicken (Bestätigung akzeptieren)
4. Klicke auf **Durchsuchen**, suche nach **„Claudian"**, überprüfe, ob es von - von Yishen Tu ist, klicke auf **Installieren** und danach auf **Aktivieren**

Das war's — Claudian erkennt die in Schritt 5/6 eingerichtete Claude-Code-CLI automatisch, keine weitere Konfiguration nötig.

---

# Teil C: Vor Kapitel 5 (Power-Usecase)

## Schritt 8: Kern-Plugins prüfen

Die drei Werkzeuge, mit denen du in Kapitel 5 hauptsächlich arbeitest, sind **schon in Obsidian eingebaut** — du musst nichts herunterladen, nur prüfen, ob sie eingeschaltet sind:

Öffne **Einstellungen** → **Obsidian-Erweiterungen**. Dort steht eine Liste mit Schaltern; such nach diesen dreien und stell sicher, dass der Schalter jeweils an ist:

| Kern-Plugin   | Wofür (Kapitel 5)                                       |
| ------------- | -------------------------------------------------------- |
| **Bases**     | Datenbank-artige Ansichten ohne Abfragesprache            |
| **Canvas**    | Unendliches Whiteboard für Notizen und Skizzen            |
| **Templates** | Vorlagen mit fertigem OKF-[[Frontmatter]]-Gerüst          |

*Schnellcheck ohne Umweg über die Einstellungen: Befehlspalette öffnen (`Strg/Cmd + P`) und den Namen tippen. Erscheinen passende Befehle, ist das Plugin aktiv.*

*Taucht **Bases** gar nicht erst in der Liste auf, ist deine Obsidian-Version zu alt — unter Einstellungen → **Über** die Version prüfen und aktualisieren.*

## Schritt 9: Cron installieren (optional)

Eine einzige Externe Erweiterung — Installation genau wie bei Claudian in Schritt 7 (Einstellungen → Externe Erweiterungen → Durchsuchen → Installieren → Aktivieren):

| Plugin   | Wofür (Kapitel 5)                                            |
| -------- | ------------------------------------------------------------ |
| **Cron** | Zeitgesteuerte Automatisierung (Ausblick, ohne Pflichtübung) |

*Cron dient in Kapitel 5 nur als Ausblick, es gibt keine Pflichtübung dazu. Wer mag, kann die Installation also auch überspringen und beim Zuschauen bleiben.*

---

# Teil D: Vor dem Bonus-Kapitel Command Line (optional)

*Das Bonus-Kapitel Command Line ist freiwillig — der Pitch dazu kommt in Kapitel 4. Wenn du es nicht machst, überspring diesen Teil komplett.*

## Schritt 10: Ein besseres Windows-Terminal

*Nur relevant, wenn du Windows nutzt und in Schritt 4 gemerkt hast, dass du nur cmd/PowerShell hast — für Mac/Linux entfällt das.*

**Mit Adminrechten:** Empfehlenswert ist **[Git for Windows](https://git-scm.com/downloads)** — das bringt **Git Bash** mit, ein Terminal mit echten Unix-Befehlen (`grep`, `sort`, `ls` usw.), und deckt gleichzeitig Teil E ab. Ein Download für zwei Kapitel.

Optional zusätzlich: **Windows Terminal** aus dem Microsoft Store — bündelt cmd, PowerShell und Git Bash in einem Fenster mit Tabs. Store-Apps lassen sich meist auch ohne Adminrechte pro Benutzerkonto installieren.

**Ohne Adminrechte (z. B. Firmenrechner):** Kein Problem — du arbeitest mit dem, was schon da ist, meist **PowerShell** (startet ohne Zusatzrechte). Das Bonus-Kapitel gibt zu jedem Unix-Befehl eine PowerShell-Alternative an.

## Schritt 11: Werkzeuge für die Spaß-Übungen

Für die beiden Spielereien im Bonus-Kapitel — sind reiner Bonus, kein Muss:

| Werkzeug        | Mac/Linux                                          | Windows                                                                                     |
| --------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| **cowsay**      | `brew install cowsay` / `sudo apt install cowsay` | ohne Adminrechte: `Install-Module -Scope CurrentUser PSCowsay`                                |
| **ImageMagick** | `brew install imagemagick` / `sudo apt install imagemagick` | ohne Adminrechte: [portable ZIP-Version](https://imagemagick.org/script/download.php#windows) entpacken, `convert.exe` läuft direkt aus dem Ordner |

Blockt die IT auch das: kein Problem, die Spaß-Übungen sind Bonus, der Rest des Kapitels funktioniert ohne sie.

---

# Teil E: Vor dem Bonus-Kapitel Git (optional)

## Schritt 12: Git installieren

- **Windows:** [Git for Windows](https://git-scm.com/downloads) — falls du das in Schritt 10 schon installiert hast, bist du hier fertig
- **macOS:** `git --version` im Terminal eingeben; ist Git nicht da, bietet macOS die Installation direkt an
- **Linux:** `sudo apt install git` (oder das Äquivalent deiner Distribution)

Test: `git --version` sollte eine Versionsnummer zeigen.

---

## Offene Punkte / noch zu ergänzen

- [ ] Screenshots für Download-Button und „Ordner als Vault öffnen"
- [ ] Hinweise für typische Stolperfallen (z. B. Sicherheitswarnung beim ersten Öffnen, falsche ZIP-Entpackung)
- [ ] Kurzer Check am Ende von Teil A: „Siehst du die Ordnerstruktur links? Dann ist alles bereit."
- [ ] Sicherstellen, dass die Beispiel-Notizen im tatsächlichen Vault-Download enthalten sind
- [ ] Screenshot für Community-Plugin-Suche/Installation
- [ ] Screenshot/GIF, wie die drei Windows-Terminals (cmd/PowerShell/Windows Terminal) sich optisch unterscheiden
- [ ] Testen, ob die Windows-„Execution Policy" bei typischer Workshop-Hardware (Firmenrechner) den Installationsbefehl blockiert
- [ ] Prüfen, ob Claude-Code-Installation + Anmeldung realistisch in die Session-Zeit passt
- [ ] Teil E ist vorläufig — muss mit `bonus-git/` abgeglichen werden, sobald das Kapitel ausgearbeitet ist
