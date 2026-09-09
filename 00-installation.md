# Installation

## Worum geht es hier?

Willkommen zur Obsidian Installationsparty! Versteht es als Party, nicht als Prüfung: Quatschen und lachen ist ausdrücklich gewünscht, Übungen sind freiwillig, überfliegen ist ok. Wir arbeiten zu viert in Breakout-Rooms, im Idealfall mit einer Mentorin pro drei Teilnehmerinnen. Der Inhalt hier ist ein sehr reichhaltiges Buffet, ihr entscheidet, wonach auch Euch ist, wie viel ihr wollt und was ihr euch vielleicht für später einpackt. 

Was der Workshop insgesamt bietet, steht im [[README]] — hier geht's direkt an die Installation.

## Was wird wann gebraucht?

| Kapitel                                                 | Werkzeug                                            | Teil                                                     |
| ------------------------------------------------------- | --------------------------------------------------- | -------------------------------------------------------- |
| `01-obsidian-und-markdown/`                             | Obsidian + Vault                                    | **[[#Teil A: Basis — vor Kapitel 1\|Teil A]]**           |
| `02-sync-mehrere-geraete/`, `03-vaults-und-graph-view/` | nichts zusätzlich                                   | —                                                        |
| `04-ki-second-brain/`                                   | Terminal, Claude Code CLI, Claudian — Web Clipper   | **[[#Teil B: Vor Kapitel 4 (KI-Second-Brain)\|Teil B]]** |
| Bonus-Kapitel (Power-Usecase, Command Line, Git)        | siehe [[00-installation-bonus\|Installation Bonus]] | Teil C–E                                                 |

Nur **[[#Teil A: Basis — vor Kapitel 1|Teil A]]** ist Pflicht, bevor es losgeht. Wenn Du sicher weißt, dass Du Claude in Obsidian nutzen willst, dann mach Teil B am besten direkt mit. Denn das ist der schwierigste Teil. Die Unterordner durcharbeiten kannst Du auch alleine, wenn alles installiert ist. 

---

# Teil A: Basis — vor Kapitel 1

## Schritt 1: Das Vault von GitHub herunterladen

Repo: https://github.com/P3nny/obsidian-installationsparty

1. Öffne das Repo im Browser
2. Klicke auf den grünen Button `Code`
3. Wähle `Download ZIP`
4. Entpacke die ZIP-Datei an einem Ort, an dem Du damit arbeiten möchtest

![[github_code_zip.png]]

*(Wer Git schon kennt, kann `git clone` benutzen — mehr dazu im Bonus-Kapitel Git.)*

## Schritt 2: Obsidian installieren

- Rufe die Webseite [obsidian.md](https://obsidian.md) auf
- Lade die passende Version für dein Betriebssystem herunter
- Installiere Obsidian wie Du sonst Programme installierst
- Startdialog erst mal stehen lassen — geht direkt weiter mit [[#Schritt 3: Vault in Obsidian öffnen|Schritt 3]]

## Schritt 3: Vault in Obsidian öffnen

1. Im Startdialog **nicht** auf „Schnellstart" klicken, sondern auf **„Ordner als Vault öffnen"**
2. Wähle den in [[#Schritt 1: Das Vault von GitHub herunterladen|Schritt 1]] entpackten Ordner aus
3. Obsidian öffnet den Ordner als Vault — du siehst links die Dateistruktur mit allen Kapiteln

*Schon auf „Schnellstart" geklickt und in einem leeren Vault gelandet? Unten links auf das Vault-Symbol klicken → **Vaults verwalten** → **Ordner als Vault öffnen** — weiter bei Punkt 2.*

![[vault.png]]

Damit ist Teil A abgeschlossen.

**Weiter geht's:** Auf zu [[1-obsidian-grundlagen|Kapitel 1]].

---

# Teil B: Vor Kapitel 4 (KI-Second-Brain)

In Kapitel 4 steuerst du Claude direkt aus Obsidian heraus. Dafür brauchst du drei Bausteine: ein Terminal, die Claude Code CLI und das Obsidian-Plugin Claudian.

![[keine_panik.png]]

## Schritt 4: Terminal finden (nur Windows)

*Mac/Linux: eingebautes Terminal reicht, Schritt überspringen.*

1. Windows-Taste drücken, **„Terminal"** eingeben. Vorhanden? → öffnen.
2. Sonst: **„PowerShell"** eingeben und öffnen.
3. Sonst: **„cmd"** / **„Eingabeaufforderung"** — die gibt es garantiert.

**Welche Shell läuft darin?** Steht am Zeilenanfang `PS C:\...>` → **PowerShell**. Steht dort nur `C:\...>` ohne `PS` → **cmd**. Merk dir das — davon hängt in [[#Schritt 5: Claude Code CLI installieren|Schritt 5]] ab, welchen Befehl du kopierst.

*Nichts gefunden? Windows-Taste + R, `cmd` eintippen, Enter. Blockt die IT beide Terminals komplett: siehe Notausgang am Ende von [[#Schritt 5: Claude Code CLI installieren|Schritt 5]].*

## Schritt 5: Claude Code CLI installieren

Das Werkzeug, mit dem Claudian ([[#Schritt 7: Claudian in Obsidian installieren|Schritt 7]]) Claude steuert. Ein Copy-Paste-Befehl, kein Adminrecht nötig. Kopiere folgenden Code in dein Terminal (Welches das ist hast du in  [[#Schritt 4: Terminal finden (nur Windows)|Schritt 4]] herausgefunden:

**macOS / Linux:**
```
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows PowerShell:**
```
irm https://claude.ai/install.ps1 | iex
```

**Windows Eingabeaufforderung (cmd):**
```
curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd
```

**Terminal-Fenster komplett schließen und neu öffnen.** Dann testen:
```
claude --version
```
Versionsnummer da: weiter zu Schritt 6. Kommt `not in PATH`/`command not found`: **das ist eher die Regel als die Ausnahme**, kein Grund zur Sorge — weiter unten.

*Tipp: Kopieren-Symbol erscheint rechts oben, wenn du mit der Maus über einen Codeblock fährst.*

**Fehler schon beim Installieren?**

- `'irm' wird nicht als Befehl erkannt` → du bist in cmd, hast aber die PowerShell-Zeile genommen
- `Die Token "&&" ist kein gültiges Anweisungstrennzeichen` → umgekehrt: PowerShell mit cmd-Zeile
- **„Execution Policy"** → Sicherheitseinstellung mancher Firmenrechner; cmd-Zeile probieren, sonst IT/Coachin fragen

### `claude --version` findet nichts — [[PATH]] von Hand eintragen

Prüfe zuerst, ob das Programm überhaupt da ist:

**Windows PowerShell:**
```
& "$env:USERPROFILE\.local\bin\claude.exe" --version
```

**Windows cmd:**
```
"%USERPROFILE%\.local\bin\claude.exe" --version
```

**macOS / Linux:**
```
~/.local/bin/claude --version
```

**Versionsnummer da?** Programm ist installiert, nur der PATH-Eintrag fehlt:

- **Windows:** Windows-Taste → „Umgebungsvariablen" → **„Umgebungsvariablen für dieses Konto bearbeiten"** (kein Adminrecht nötig) → bei **Path** → **Bearbeiten** → **Neu** → diesen Pfad einfügen:
  ```
  %USERPROFILE%\.local\bin
  ```
  → **OK**. Neues Terminal öffnen.
- **macOS / Linux:** In alle drei möglichen Dateien gleichzeitig eintragen, spart das Rätselraten, welche Shell läuft:
  ```
  echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
  echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bash_profile
  echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
  ```
  Terminal komplett schließen und neu öffnen.

Danach nochmal:
```
claude --version
```

**Auch der vollständige Pfad (die drei Testbefehle oben) zeigt nichts?** Dann ist die Installation selbst schiefgegangen — den Installationsbefehl aus [[#Schritt 5: Claude Code CLI installieren|Schritt 5]] nochmal ausführen, diesmal auf Fehlermeldungen achten statt sie zu überlesen.

*Notausgang ohne Terminal: Blockt die IT beides komplett, gibt es die **Claude Desktop App** ([claude.com/download](https://claude.com/download)) — grafisch statt Kommandozeile, aber Pro/Max-Abo nötig (kein API-Key) und läuft außerhalb von Obsidian. Sag in der Session Bescheid, wenn das dein Fall ist.*

## Schritt 6: Bei Claude anmelden

**Mit Pro-/Max-Abo:** `claude` ins Terminal tippen, Browser-Login folgen. *Möchtest du nicht, dass deine Vault-Inhalte fürs KI-Training verwendet werden können, prüfe den Schalter unter [claude.ai/settings/data-privacy-controls](https://claude.ai/settings/data-privacy-controls) — siehe auch [[Claude Code Datenfluss]].*

**Ohne Abo** (Free-Tarif reicht nicht): API-Key nötig.

1. **console.anthropic.com** öffnen, registrieren
2. Unter **Billing** Zahlungsmethode hinterlegen, Guthaben aufladen (5 $ reichen)
3. Unter **API Keys** → **Create Key**, Key **sofort kopieren** (beginnt mit `sk-ant-api03-…`)
4. `claude` im Terminal starten, Key einfügen

## Schritt 7: Claudian in Obsidian installieren

*Obsidian-Bezeichnungen hier auf Deutsch.*

1. **Einstellungen** (Zahnrad unten links)
2. **Externe Erweiterungen** (= „Community plugins")
3. Falls **eingeschränkter Modus** aktiv: `Eingeschränkten Modus verlassen` klicken
4. **Durchsuchen** → **„Claudian"** (von Yishen Tu) → **Installieren** → **Aktivieren**

![[erweiterungen.png]]

Claudian findet die CLI aus [[#Schritt 5: Claude Code CLI installieren|Schritt 5]]/[[#Schritt 6: Bei Claude anmelden|Schritt 6]] normalerweise von allein.

**Findet Claudian die CLI nicht?** Dasselbe [[PATH]]-Thema wie in Schritt 5.

1. Obsidian komplett schließen und neu starten
2. Sonst: Pfad von Hand eintragen — im Terminal mit `where claude` (Windows) / `which claude` (Mac/Linux) ausgeben, kopieren, dann in Obsidian: **Einstellungen** → **Claudian** → Anbieter **Claude** → Feld **CLI path** einfügen

*Claudian-Oberfläche ist auf Englisch, auch bei deutschem Obsidian.*

### Direkt danach: Sicherheitsmodus auf „Safe" umstellen

Claudian startet standardmäßig im **YOLO-Modus** (führt alles sofort aus, ohne zu fragen). Für den Anfang besser: **Safe-Modus** — Claude fragt vor jeder schreibenden Aktion nach.

Schalter: **unten rechts im Claudian-Chat-Fenster** (nicht in den Obsidian-Einstellungen), Umschalter zwischen **„Safe"** und **„YOLO"**.

**Warum Safe zum Einstieg:** Du siehst, was passiert, bevor es passiert; kein Risiko für ungewollte Vault-Änderungen; du lernst nebenbei, welche Befehle Claude einsetzt. Später jederzeit auf YOLO umschaltbar.

**Zusätzliches Sicherheitsnetz, ganz ohne Bonus-Kapitel Git:** Obsidian hat ein eingebautes Kern-Plugin **„Dateiwiederherstellung"** — prüfen, ob es unter Einstellungen → Obsidian-Erweiterungen aktiviert ist. Es speichert automatisch alle paar Minuten einen Schnappschuss jeder Notiz (7 Tage aufbewahrt). Hat Claude im Safe-Modus etwas verändert, das du im Nachhinein doch nicht wolltest: Befehlspalette → **„Dateiwiederherstellung: Lokalen Verlauf öffnen"**.

**Modell-Empfehlung:** Reicht das Standardmodell nicht (z. B. bei Übung 1 in Kapitel 4, Teil 1, wo manche Modelle die Verbindung zwischen zwei Notizen übersehen), in Claudian per `/model` auf **Sonnet, Effort-Stufe „Medium"** wechseln — läuft in der Praxis sehr zuverlässig.

## Schritt 7b: Web Clipper installieren (optional)

*Für Kapitel 4, Teil 2. Optional — zwei fertige Beispiel-Clips liegen schon unter `Clippings/`.*

1. [obsidian.md/clipper](https://obsidian.md/clipper) — Version für deinen Browser installieren
2. Clipper-Symbol im Browser klicken, Workshop-Vault als Ziel wählen
3. Zielordner in **Einstellungen → Allgemein** festlegen (Standard: `Clippings/`)

Test: Artikelseite öffnen, Clipper-Symbol klicken, speichern — Notiz sollte in `Clippings/` auftauchen.

**Adminrechte?** Normalerweise nicht nötig. Blockt die IT es doch: siehe [[Ohne Adminrechte]].

**Weiter geht's:** Auf zu [[1-plugin-setup-und-chat|Kapitel 4]].

---

*Bonus-Kapitel (Power-Usecase, Command Line, Git)? Weiter mit [[00-installation-bonus|Installation Bonus]].*
