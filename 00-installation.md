# Installation

## Worum geht es hier?

Willkommen zur Obsidian Installationsparty! Versteht es bitte wirklich als Party - das hier soll Spaß machen. Quatschen und lachen ist ausdrücklich gewünscht, lernt die anderen Teilnhemer:innen ein bisschen kennen, lernt gemeinsam und tauscht euch aus. Wir arbeiten zu viert in Breakout-Rooms. Auf drei Teilnehmer:innen kommt eine Mentorin. 

Betrachtet die Inhalte hier als ein reichhaltiges Buffet - und pickt für Euch raus, worauf ihr gerade Lust habt und was ihr gerade gebrauchen könnt. Sowohl was die Kapitel angeht als auch innerhalb der Inhalte. Ihr könnt die Übungen machen, müsst ihr aber nicht. Ihr dürft gerne alles genau lesen, aber überfliegen ist auch ok. 
Vielleicht hast Du nach einer Stunde alles, was Du heute wolltest. Vielleicht nimmst Du Dir mehr Zeit.

Die Übungen sind KI-generiert und teilweise nicht intuitiv lösbar. Spring gerne direkt zum Auflösungsteil und frag bei Patricia oder deiner Mentorin nach. 
 
## Was du hier lernen kannst

- **Obsidian installieren** und die Grundidee dahinter verstehen
- **Markdown** — die einfache Auszeichnungssprache, mit der alles hier geschrieben ist
- **Vaults** — wie Obsidian deine Notizen organisiert
- **Graph-Ansicht** — wie aus verlinkten Notizen ein sichtbares Wissensnetz wird
- **Sync** — welche Wege es gibt, den Vault auf mehreren Geräten aktuell zu halten
- Installation der KI-Erweiterung **Claudian** samt Claude Code CLI
- **Web Clipper** — Artikel aus dem Browser als fertig formatierte Notiz ins Vault holen
- Der **Second-Brain-Kreislauf**: roh reinwerfen, von der KI verdichten und verlinken lassen, per Frage wiederfinden
- **Open Knowledge Format (OKF)** — ein leichtgewichtiges Format, um Notizen mit Struktur, Herkunft und Vertrauensstatus zu versehen
- **Bonus:** Grundlagen der Command Line — genug, um sich sicher zu bewegen
- **Bonus:** Git-Grundlagen — was es ist, wofür man es braucht, erster Commit und Push mit dem eigenen Vault als Repo
- Bonus **Obsidian-Power-Usecases** (Templates, Cron, Bases, Canvas )

## Wie geht's los?

Du installierst nicht alles auf einmal, sondern immer genau das, was das nächste Kapitel braucht. Für den Start reichen zwei Dinge — in dieser Reihenfolge:

1. Den **Workshop-Vault** von GitHub herunterladen und entpacken
2. **Obsidian** installieren und den entpackten Ordner direkt als Vault öffnen

*Warum erst der Ordner?* Obsidian fragt beim allerersten Start, mit welchem Vault du arbeiten willst. Liegt der Workshop-Ordner da schon auf der Platte, wählst du ihn einfach aus und bist fertig. 

Danach liegen alle weiteren Kapitel bereits im Vault vor dir. Die restlichen Werkzeuge holst du dir erst, wenn du beim jeweiligen Kapitel angekommen bist.

## Was wird wann gebraucht?

| Kapitel                               | Werkzeug zu installieren                                                  | Teil       |
| ------------------------------------- | ------------------------------------------------------------------------- | ---------- |
| `01-obsidian-und-markdown/`           | Obsidian + Vault                                                          | **[[#Teil A: Basis — vor Kapitel 1\|Teil A]]** |
| `02-sync-mehrere-geraete/` (optional) | nichts — hier wird nur verglichen und entschieden                         | —          |
| `03-vaults-und-graph-view/`           | nichts — alles schon in Obsidian eingebaut                                | —          |
| `04-ki-second-brain/`                 | Terminal, Claude Code CLI, Claude-Zugang, Claudian — optional Web Clipper | **[[#Teil B: Vor Kapitel 4 (KI-Second-Brain)\|Teil B]]** |
| `bonus-power-usecases-obsidian/` (optional) | Templates, Bases, Canvas (alle nativ) — optional Cron               | **[[#Teil C: Vor dem Bonus-Kapitel Power-Usecase (optional)\|Teil C]]** |
| `bonus-command-line/` (optional)      | ggf. besseres Windows-Terminal, cowsay, ImageMagick                       | **[[#Teil D: Vor dem Bonus-Kapitel Command Line (optional)\|Teil D]]** |
| `bonus-git/` (optional)               | Git + GitHub-Konto, Erweiterung „Obsidian Git"                            | **[[#Teil E: Vor dem Bonus-Kapitel Git (optional)\|Teil E]]** |

Nur **[[#Teil A: Basis — vor Kapitel 1|Teil A]]** ist Pflicht, bevor es losgeht. Alles andere kommt zum passenden Zeitpunkt in der Session.

---

# Teil A: Basis — vor Kapitel 1

## Schritt 1: Das Vault von GitHub herunterladen

Das komplette Workshop-Material liegt in diesem Repo:
https://github.com/P3nny/obsidian-installationsparty

So kommst du an die Dateien:

1. Öffne das Repo im Browser
2. Klicke auf den grünen Button `Code`
3. Wähle `Download ZIP`
4. Entpacke die ZIP-Datei an einem Ort, an dem Du damit arbeiten möchtest

![[github_code_zip.png]]

*(Wer Git schon kennt, kann `git clone` benutzen — mehr dazu im Bonus-Kapitel Git.)*

## Schritt 2: Obsidian installieren

- Rufe die Webseite [obsidian.md](https://obsidian.md) auf
- Lade die passende Version für dein Betriebssystem herunter (Windows / Mac / Linux)
- Installiere Obsidian wie Du sonst Programmie installierst
- Öffne Obsidian noch nicht bzw. lass den Startdialog erst mal stehen — der ist gleich [[#Schritt 3: Vault in Obsidian öffnen|Schritt 3]]

## Schritt 3: Vault in Obsidian öffnen

1. Im Startdialog **nicht** auf „Schnellstart" klicken, sondern auf **„Ordner als Vault öffnen"**
2. Wähle den in [[#Schritt 1: Das Vault von GitHub herunterladen|Schritt 1]] entpackten Ordner aus
3. Obsidian öffnet den Ordner als Vault — du siehst links die Dateistruktur mit allen Kapiteln

*Schon auf „Schnellstart" geklickt und in einem leeren Vault gelandet? Kein Drama: unten links auf das Vault-Symbol (Schrank - Pfeil hoch/runter) klicken → **Vaults verwalten** → **Ordner als Vault öffnen** — und dann weiter bei Punkt 2.*

Kurzer Check: Siehst du die Ordnerstruktur links? Dann ist alles bereit.

![[vault.png]]

Damit ist Teil A abgeschlossen. Die Kapitel 1 bis 3 brauchen nichts weiter als Obsidian selbst.

**Weiter geht's:** Auf zu [[1-obsidian-grundlagen|Kapitel 1]].

---

# Teil B: Vor Kapitel 4 (KI-Second-Brain)

In Kapitel 4 steuerst du Claude direkt aus Obsidian heraus. Dafür brauchst du drei Bausteine: ein Terminal, die Claude Code CLI und das Obsidian-Plugin Claudian.

Damit begegnet dir hier zum ersten Mal das **Terminal** — das Fenster mit dem blinkenden Cursor, in das man Befehle tippt. Dass das im ersten Moment einschüchternd wirkt, geht fast allen so. Tatsächlich ist es nur eine andere Art, dem Rechner zu sagen, was er tun soll: tippen statt klicken. Auswendig lernen musst du nichts, jeden Befehl findest du hier zum Kopieren — und wer sich später darauf einlässt, hat damit erstaunlich schnell ein Werkzeug in der Hand, das frau nicht mehr hergeben will (mehr dazu im Bonus-Kapitel Command Line).

![[keine_panik.png]]

## Schritt 4: Terminal finden (nur Windows)

*Mac- und Linux-Nutzerinnen haben mit dem eingebauten Terminal schon alles, was sie brauchen, und können diesen Schritt überspringen.*

Windows hat nicht nur ein Terminal, sondern mehrere — mit unterschiedlichen Befehlen. Erstmal eines öffnen:

1. Drücke die Windows-Taste und tippe **„Terminal"**. Erscheint eine App namens **Terminal**? → öffnen.
2. Falls nicht: Tippe stattdessen **„PowerShell"** und öffne **Windows PowerShell** — das ist auf praktisch jedem Windows-Rechner vorinstalliert.
3. Falls auch das nicht auftaucht: Tippe **„cmd"** oder **„Eingabeaufforderung"** — die gibt es garantiert.

**Wichtig: Der Name der App verrät noch nicht, womit du gerade tippst.** „Windows Terminal" ist nur das Fenster; darin läuft eine sogenannte *Shell* — meist PowerShell, manchmal cmd. Welche es ist, siehst du erst im geöffneten Fenster an der ersten Zeile:

- Steht am Zeilenanfang `PS C:\Users\DeinName>` → **PowerShell** (auch wenn oben „Terminal" steht)
- Steht dort `C:\Users\DeinName>` ohne das `PS` → **cmd / Eingabeaufforderung**

Merk dir, was bei dir steht — davon hängt in [[#Schritt 5: Claude Code CLI installieren|Schritt 5]] ab, welchen Befehl du kopierst.

*Im Windows Terminal kannst du übrigens per `+`-Symbol bzw. dem kleinen Pfeil daneben zwischen den Shells wechseln; jeder Tab kann eine andere sein.*

*Und wenn ich gar nichts davon finde?* Das kommt praktisch nicht vor — Claude Code setzt Windows 10 (Version 1809) oder neuer voraus, und dort ist mindestens die Eingabeaufforderung immer installiert. Findet die Suche nichts, liegt es meist an der Windows-Suche selbst: Drücke dann `Windows-Taste + R`, tippe `cmd` und drücke Enter. Blockt die IT deines Firmenrechners tatsächlich beide Terminals, gibt es einen Ausweg ganz ohne Kommandozeile — siehe den Kasten am Ende von [[#Schritt 5: Claude Code CLI installieren|Schritt 5]].

## Schritt 5: Claude Code CLI installieren

Das ist das Werkzeug, mit dem Claudian ([[#Schritt 7: Claudian in Obsidian installieren|Schritt 7]]) Claude tatsächlich steuert. Ein einziger Copy-Paste-Befehl, offizielle Software von Anthropic — kein Adminrecht nötig. Nimm die Zeile, die zu deinem Terminal aus [[#Schritt 4: Terminal finden (nur Windows)|Schritt 4]] passt:

**macOS / Linux**:  
curl -fsSL https://claude.ai/install.sh | bash

Windows **PowerShell**: 
irm https://claude.ai/install.ps1 | iex

Windows **Eingabeaufforderung (cmd)**: 
curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd

Test, ob's geklappt hat. Tippe in deinem Terminal: 
```claude --version```
Das sollte eine Versionsnummer zeigen.

**Wenn eine Fehlermeldung kommt:**

- `'irm' wird nicht als Befehl erkannt` → Du bist in cmd, hast aber den PowerShell-Befehl genommen. Nimm die cmd-Zeile.
- `Die Token "&&" ist kein gültiges Anweisungstrennzeichen` → Umgekehrt: Du bist in PowerShell und hast die cmd-Zeile genommen.
- Etwas mit **„Execution Policy"** → Eine Sicherheitseinstellung mancher Firmenrechner, die PowerShell-Skripte blockiert. Probier in diesem Fall die cmd-Zeile; hilft das nicht, bei der IT nachfragen oder in der Session eine Coachin fragen.
- **`claude` wird nicht als Befehl erkannt / `command not found`, obwohl die Installation durchlief** → Häufigster Fall, eigener Abschnitt gleich unten.

### Wenn `claude --version` „not in PATH" sagt ( Patricia um Hilfe bitten)

Die Installation hat trotzdem geklappt — dein Terminal weiß nur noch nicht, wo das Programm liegt. Terminals suchen Befehle ausschließlich in einer Liste von Ordnern, dem sogenannten **PATH**. Der Installer trägt seinen Ordner dort ein, aber ein bereits geöffnetes Terminal-Fenster liest diese Liste nicht neu ein.

**Erste Maßnahme (löst es fast immer):** Terminal-Fenster komplett schließen, ein neues öffnen, `claude --version` erneut tippen.

Hilft das nicht, prüfe zuerst, ob das Programm überhaupt da ist — tippe die vollständige Adresse:

| System                | Testbefehl                                    |
| --------------------- | --------------------------------------------- |
| Windows (PowerShell)  | `& "$env:USERPROFILE\.local\bin\claude.exe" --version` |
| Windows (cmd)         | `"%USERPROFILE%\.local\bin\claude.exe" --version` |
| macOS / Linux         | `~/.local/bin/claude --version`               |

Kommt jetzt eine Versionsnummer, fehlt wirklich nur der PATH-Eintrag:

`where claude` (Windows) bzw. `which claude` (Mac/Linux) - gibt den Pfad

- **Windows:** Windows-Taste drücken, „Umgebungsvariablen" tippen, **„Umgebungsvariablen für dieses Konto bearbeiten"** öffnen (geht ohne Adminrechte). Oben bei **Path** auf **Bearbeiten** → **Neu** → Pfad von oben eintragen, Beispiel:`%USERPROFILE%\.local\bin` eintragen → mit **OK** bestätigen. Danach ein **neues** Terminal öffnen.
- **macOS / Linux:** Zeile `export PATH="$HOME/.local/bin:$PATH"` ans Ende der Datei `~/.zshrc` (macOS) bzw. `~/.bashrc` (meist Linux) hängen, Terminal neu öffnen.

*Und wenn auch der vollständige Pfad nichts findet?* Dann ist die Installation tatsächlich schiefgegangen — Befehl aus der Tabelle oben nochmal ausführen und auf Fehlermeldungen achten.

*Merk dir den Pfad, der bei dir funktioniert hat.* In [[#Schritt 7: Claudian in Obsidian installieren|Schritt 7]] kann es sein, dass Claudian ihn braucht — ausgeben lassen kannst du ihn dir jederzeit mit dem Befehl von oben.

*Optional für Windows: Wenn du [Git for Windows](https://git-scm.com/downloads/win) installiert hast, nutzt Claude Code dessen Git Bash und kann Befehle etwas komfortabler ausführen — ohne läuft alles über PowerShell. Nötig ist das nicht, und du kannst es jederzeit nachholen. Wer das optionale Bonus-Kapitel Command Line oder Git machen will, installiert es dort ohnehin ([[#Teil D: Vor dem Bonus-Kapitel Command Line (optional)|Teil D]] bzw. [[#Teil E: Vor dem Bonus-Kapitel Git (optional)|Teil E]]).*

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
3. Falls der **eingeschränkte Modus** noch aktiv ist: einmal auf `Eingeschränkten Modus verlassen`klicken
4. Klicke auf **Durchsuchen**, suche nach **„Claudian"**, überprüfe, ob es von - von Yishen Tu ist, klicke auf **Installieren** und danach auf **Aktivieren**

![[erweiterungen.png]]

In der Regel war's das: Claudian findet die in [[#Schritt 5: Claude Code CLI installieren|Schritt 5]]/[[#Schritt 6: Bei Claude anmelden|Schritt 6]] eingerichtete Claude-Code-CLI von allein.

**Falls Claudian meldet, es finde die CLI nicht:** Das ist dasselbe PATH-Thema wie in [[#Schritt 5: Claude Code CLI installieren|Schritt 5]] — Obsidian ist ein Fenster-Programm und kennt die Ordner-Liste deines Terminals nicht zwangsläufig.

1. **Obsidian einmal komplett schließen und neu starten.** Wurde der PATH nach dem Obsidian-Start geändert, reicht das oft schon.
2. Hilft das nicht: Pfad von Hand eintragen. Lass ihn dir im Terminal mit `where claude` (Windows) bzw. `which claude` (Mac/Linux) ausgeben und kopiere die Zeile. Dann in Obsidian: **Einstellungen** → links unter den Erweiterungen **Claudian** → beim Anbieter **Claude** das Feld **CLI path** — Pfad einfügen, fertig.

*Die Claudian-Oberfläche ist auf Englisch, auch wenn Obsidian selbst auf Deutsch läuft — „CLI path" heißt dort also wirklich so.*
Links in deiner Weekzeugleiste sollte jetzt ein kleiner Roboter erschienen sein.

## Schritt 7b: Web Clipper installieren (optional)

*Für Kapitel 4, Teil 2. Optional — im Vault liegen unter `Clippings/` zwei fertige Beispiel-Clips, mit denen alle Übungen genauso funktionieren.*

Der **Obsidian Web Clipper** ist eine Browser-Erweiterung von Obsidian selbst: Ein Klick, und ein Artikel landet als saubere Markdown-Notiz mit ausgefüllten Eigenschaften in deinem Vault.

1. [obsidian.md/clipper](https://obsidian.md/clipper) aufrufen und die Version für deinen Browser installieren
2. Auf das Clipper-Symbol in der Browser-Leiste klicken. Beim ersten Mal fragt er, in welches Vault gespeichert werden soll — den Workshop-Vault auswählen.
3. Unter **Einstellungen → Allgemein** kannst du den Zielordner festlegen. Standard ist `Clippings/`; genau dort liegen auch die Beispiel-Clips.

Test: Irgendeine Artikelseite öffnen, Clipper-Symbol anklicken, speichern — die Notiz sollte danach in Obsidian unter `Clippings/` auftauchen.

**Adminrechte?** Normalerweise nicht nötig. Falls die IT es doch blockt: siehe [[Ohne Adminrechte]].

*Voraussetzung ist ein installiertes Obsidian auf demselben Gerät — der Clipper schreibt direkt in dein lokales Vault, es gibt keinen Cloud-Zwischenspeicher und kein Konto.*

**Weiter geht's:** Auf zu [[1-plugin-setup-und-chat|Kapitel 4]].

---

# Teil C: Vor dem Bonus-Kapitel Power-Usecase (optional)

*Wie die anderen Bonus-Kapitel freiwillig — wenn Du das nicht bearbeiten möchtest, überspring diesen Teil komplett.*

## Schritt 8: Kern-Plugins prüfen

Die drei Werkzeuge, mit denen du im Bonus-Kapitel Power-Usecase hauptsächlich arbeitest, sind **schon in Obsidian eingebaut** — du musst nichts herunterladen, nur prüfen, ob sie eingeschaltet sind:

Öffne **Einstellungen** → **Obsidian-Erweiterungen**. Dort steht eine Liste mit Schaltern; such nach diesen dreien und stell sicher, dass der Schalter jeweils an ist:

| Kern-Plugin  | Wofür                                          |
| ------------ | ---------------------------------------------- |
| **Vorlagen** | Vorlagen mit fertigem OKF-Frontmatter-Gerüst   |
| **Basen**    | Datenbank-artige Ansichten ohne Abfragesprache |
| **Canvas**   | Unendliches Whiteboard für Notizen und Skizzen |

*Schnellcheck ohne Umweg über die Einstellungen: Befehlspalette öffnen (`Strg/Cmd + P`) und den Namen tippen. Erscheinen passende Befehle, ist das Plugin aktiv.*

*Taucht **Basen** gar nicht erst in der Liste auf, ist deine Obsidian-Version zu alt — unter Einstellungen → **Über** die Version prüfen und aktualisieren.*

## Schritt 9: Cron installieren (optional)

Eine einzige Externe Erweiterung — Installation genau wie bei Claudian in [[#Schritt 7: Claudian in Obsidian installieren|Schritt 7]] (Einstellungen → Externe Erweiterungen → Durchsuchen → Installieren → Aktivieren):

| Plugin   | Wofür                                                        |
| -------- | ------------------------------------------------------------ |
| **Cron** | Zeitgesteuerte Automatisierung (Ausblick, ohne Pflichtübung) |

*Cron dient im Bonus-Kapitel nur als Ausblick, es gibt keine Pflichtübung dazu. Wer mag, kann die Installation also auch überspringen und beim Zuschauen bleiben.*

**Weiter geht's:** Auf zu [[1-power-usecase|Bonus-Kapitel Power-Usecase]].

---

# Teil D: Vor dem Bonus-Kapitel Command Line (optional)

*Das Bonus-Kapitel Command Line ist freiwillig — wenn Du das nicht bearbeiten möchtest, überspring diesen Teil komplett.*

## Schritt 10: Ein besseres Windows-Terminal

*Nur für Windows — Mac/Linux können diesen Schritt überspringen.*

**Empfohlen für dieses Kapitel, unabhängig davon, was du in [[#Schritt 4: Terminal finden (nur Windows)|Schritt 4]] vorgefunden hast:** **[Git for Windows](https://git-scm.com/downloads)** — das bringt **Git Bash** mit, ein Terminal mit echten Unix-Befehlen (`grep`, `sort`, `wc`, `uniq` usw.), und deckt gleichzeitig [[#Teil E: Vor dem Bonus-Kapitel Git (optional)|Teil E]] ab. Ein Download für zwei Kapitel. Ohne Git Bash brauchst du für einige Befehle im Bonus-Kapitel PowerShell-Alternativen, und manche (`grep`, `wc`, `uniq`) gibt es in der klassischen Eingabeaufforderung gar nicht.

Optional zusätzlich: **Windows Terminal** aus dem Microsoft Store — bündelt cmd, PowerShell und Git Bash in einem Fenster mit Tabs.

**Keine Adminrechte (z. B. Firmenrechner)?** Siehe [[Ohne Adminrechte]] — kurz gesagt: Du bleibst bei PowerShell, das Bonus-Kapitel gibt zu jedem Unix-Befehl eine Alternative dafür an.

## Schritt 11: Werkzeuge für die Spaß-Übungen

Für die beiden Spielereien im Bonus-Kapitel — sind reiner Bonus, kein Muss:

| Werkzeug        | Mac/Linux                                          | Windows |
| --------------- | --------------------------------------------------- | ------- |
| **cowsay**      | `brew install cowsay` / `sudo apt install cowsay`   | `Install-Module -Name CowsaySharp -Scope CurrentUser` |
| **ImageMagick** | `brew install imagemagick` / `sudo apt install imagemagick` | Installer von [imagemagick.org](https://imagemagick.org/script/download.php) |

**Keine Adminrechte?** Beide gehen auch ohne — siehe [[Ohne Adminrechte]]. Blockt die IT sogar das: kein Problem, die Spaß-Übungen sind Bonus, der Rest des Kapitels funktioniert ohne sie.

**Weiter geht's:** Auf zu [[1-command-line|Bonus-Kapitel Command Line]].

---

# Teil E: Vor dem Bonus-Kapitel Git (optional)

## Schritt 12: Git installieren

- **Windows:** [Git for Windows](https://git-scm.com/downloads) — falls du das in [[#Schritt 10: Ein besseres Windows-Terminal|Schritt 10]] schon installiert hast, bist du hier fertig
- **macOS:** `git --version` im Terminal eingeben; ist Git nicht da, bietet macOS die Installation direkt an
- **Linux:** `sudo apt install git` (oder das Äquivalent deiner Distribution)

Test: `git --version` sollte eine Versionsnummer zeigen.

*Keine Adminrechte? Siehe [[Ohne Adminrechte]] für eine portable Variante ganz ohne Installation.*

## Schritt 13: GitHub-Konto anlegen

Um deinen Vault ins Netz zu laden, brauchst du ein Konto bei einem Git-Dienst. Wir nutzen **GitHub** — ein kostenloses Konto reicht völlig, auch für private Repositories.

1. [github.com](https://github.com) aufrufen, **Sign up**
2. Mit E-Mail-Adresse registrieren, Benutzernamen wählen, Passwort im Passwort-Manager speichern
3. E-Mail-Adresse bestätigen

*Hast du schon ein GitHub-Konto, ist hier nichts zu tun. Wie du dich beim ersten `git push` anmeldest, klärt das Bonus-Kapitel Git — dein normales Konto-Passwort funktioniert dafür nämlich nicht.*

## Schritt 14: Erweiterung „Obsidian Git" installieren

Damit du Git im Alltag nicht über das Terminal bedienen musst: Einstellungen → **Externe Erweiterungen** → **Durchsuchen** → nach **„Obsidian Git"** suchen, installieren, aktivieren.

*Die Einrichtung im Kapitel läuft trotzdem einmal von Hand durch — verstehen, was passiert, bevor es ein Knopf übernimmt.*

**Weiter geht's:** Auf zu [[1-git|Bonus-Kapitel Git]].

---

