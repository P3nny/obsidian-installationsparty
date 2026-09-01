# 00 – Vorbereitung

## Worum geht's in diesem Kapitel?

Bevor es mit Markdown, dem Open Knowledge Format oder KI-Workflows losgeht, brauchst du zwei Dinge:

1. **Obsidian** auf deinem Rechner installiert
2. Das **Workshop-Vault** von GitHub heruntergeladen und in Obsidian geöffnet

Danach hast du alle weiteren Kapitel bereits vor dir liegen — direkt im Vault, als Notizen, die du nach und nach durcharbeitest.

**Zwei Pfade durch dieses Kapitel:**

Nicht alles muss gleich zu Beginn installiert werden — manches braucht ihr erst, wenn ihr bei einem bestimmten späteren Kapitel ankommt. Deshalb ist dieses Kapitel zweigeteilt:

- **Teil A – Minimal-Start:** Das hier machst du ganz am Anfang. Reicht, um direkt mit Kapitel 1 loszulegen und bis Kapitel 4 durchzukommen. Dauert bei einer glatten Installation ca. 20 Minuten, mit typischen Stolperfallen eher 35–40.
- **Teil B/C – bei Bedarf später:** Diese Schritte holt ihr euch erst dazu, wenn die Gruppe tatsächlich bei Kapitel 3 bzw. 5 ankommt — nicht vorher. So verbrennt niemand Zeit mit einer Installation für ein Kapitel, das an diesem Tag vielleicht gar nicht mehr drankommt.

---

# Teil A: Minimal-Start (vor Kapitel 1)

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

Für den Power-Usecase in Kapitel 4 brauchst du zwei zusätzliche Plugins. Die installierst du am besten schon jetzt, damit später keine Zeit für Setup drauf geht.

*Hinweis: Obsidian ist standardmäßig auf Deutsch — die folgenden Bezeichnungen entsprechen der deutschen Version.*

1. Öffne die **Einstellungen** (Zahnrad-Symbol unten links)
2. Gehe zu **Externe Erweiterungen** (das ist die deutsche Bezeichnung für „Community plugins")
3. Falls der **eingeschränkte Modus** noch aktiv ist: einmal auf **Eingeschränkten Modus deaktivieren** klicken (Bestätigung akzeptieren)
4. Klicke auf **Durchsuchen**, suche nach jedem der folgenden Plugins, klicke jeweils auf **Installieren** und danach auf **Aktivieren**:

| Plugin | Wofür (Kapitel 4) |
|---|---|
| **Templater** | Dynamische Templates mit dem OKF-Frontmatter-Gerüst |
| **Cron** | Zeitgesteuerte Automatisierung (Ausblick, ohne Pflichtübung) |

*Canvas, das eingebaute Plugin „Templates" und die native Funktion „Bases" (Datenbank-artige Ansichten ohne Abfragesprache, unter **Obsidian-Erweiterungen**) brauchen keine Installation — die sind schon in Obsidian dabei, ggf. nur unter Einstellungen → Obsidian-Erweiterungen zu aktivieren.*

## Schritt 5: Windows – welches Terminal habe ich?

*Nur relevant, wenn du Windows nutzt. Mac- und Linux-Nutzerinnen haben mit dem eingebauten Terminal schon alles, was sie brauchen, und können diesen Schritt überspringen.*

Windows hat nicht nur ein Terminal, sondern mehrere — mit unterschiedlichen Fähigkeiten. Ein kurzer Check jetzt reicht für den Minimal-Start; die eigentliche Installation eines besseren Terminals (falls gewünscht) kommt erst in Teil B, vor Kapitel 3.

1. Drücke die Windows-Taste und tippe **„Terminal"**. Erscheint eine App namens **Terminal** mit einem bunten Symbol? → Du hast **Windows Terminal**, die modernste Variante (bei Windows 11 meist vorinstalliert).
2. Falls nicht: Tippe stattdessen **„PowerShell"**. Erscheint **Windows PowerShell**? → Zweitbeste Option, auf praktisch jedem Windows-Rechner vorinstalliert.
3. Falls auch das nicht auftaucht: Tippe **„cmd"** oder **„Eingabeaufforderung"** — die gibt es garantiert, sie kann aber am wenigsten.
4. Bist du unsicher, welches Fenster du gerade offen hast: Tippe `$PSVersionTable.PSVersion` und drücke Enter.
   - Erscheint eine Versionsnummer → du bist in **PowerShell**.
   - Erscheint eine Fehlermeldung à la „wird nicht als Name eines Cmdlets erkannt" → du bist in **cmd / Eingabeaufforderung**.

Notiere dir kurz, welches der drei du hast — das reicht für den Minimal-Start völlig aus.

Damit ist Teil A abgeschlossen — ab hier kannst du direkt mit Kapitel 1 loslegen. Alles Weitere holt ihr euch erst, wenn ihr in der Session tatsächlich bei Kapitel 3 bzw. 5 angekommen seid.

Ab hier liegt die gesamte weitere Struktur bereits vor dir:

```
00-vorbereitung/
01-obsidian-und-markdown/
02-vaults-und-graph-view/
03-command-line/
04-power-usecase/
05-ki-erweiterung/          (inkl. Workflow-zu-OKF, Second-Brain-Übung, Vergleich der Setups)
06-okf-format/               (Vertiefung für alle, die es genauer wissen wollen)
bonus-git/
```

---

# Teil B: Vor Kapitel 3 (Command Line)

## Ein besseres Windows-Terminal (optional)

*Nur relevant, wenn du Windows nutzt und in Schritt 5 gemerkt hast, dass du nur cmd/PowerShell hast — für Mac/Linux entfällt das.*

### Was, wenn ich Adminrechte auf meinem Rechner habe

Empfehlenswert ist die Installation von **[Git for Windows](https://git-scm.com/downloads)** — das bringt **Git Bash** mit, ein Terminal mit echten Unix-Befehlen (`grep`, `sort`, `ls` usw.), und wird ohnehin im Bonus-Kapitel Git gebraucht. Ein Download deckt also zwei Kapitel ab.

Optional zusätzlich: **Windows Terminal** aus dem Microsoft Store — bündelt cmd, PowerShell und Git Bash in einem Fenster mit Tabs. Store-Apps lassen sich meist auch ohne Adminrechte pro Benutzerkonto installieren.

### Was, wenn ich keine Adminrechte habe (z. B. Firmenrechner)

Das ist kein Problem — du arbeitest einfach mit dem, was schon da ist, meist **PowerShell** (startet ohne Zusatzrechte). Kapitel 3 gibt zu jedem Unix-Befehl eine PowerShell-Alternative an.

Für die Spaß-Übungen in Kapitel 3 gibt es Varianten, die ganz ohne Installation auskommen:

- **ImageMagick (für das GIF-Beispiel):** Die [portable ZIP-Version](https://imagemagick.org/script/download.php#windows) einfach entpacken — `convert.exe` läuft direkt aus dem entpackten Ordner heraus, ganz ohne Installer.
- **cowsay:** Das PowerShell-Modul lässt sich pro Benutzerkonto installieren, ganz ohne Adminrechte: `Install-Module -Scope CurrentUser PSCowsay`
- Blockt die IT auch das: kein Problem, die Spaß-Übungen sind Bonus, kein Muss für den Rest des Workshops.

---

# Teil C: Vor Kapitel 5 (KI-Erweiterung)

## Schritt 6: Ollama installieren (lokale KI für Kapitel 5)

Für Kapitel 5 (KI-Erweiterung) brauchst du eine KI, mit der Obsidian sprechen kann. Als Standard nutzen wir **Ollama** — läuft komplett lokal auf deinem Rechner, ist kostenlos und braucht **keine Adminrechte** (installiert sich automatisch in dein Benutzerprofil, auch unter Windows).

1. Rufe [ollama.com/download](https://ollama.com/download) auf und lade die Version für dein Betriebssystem
2. Installiere Ollama ganz normal (Doppelklick auf die Installationsdatei, durchklicken)
3. Öffne dein Terminal (siehe Schritt 5 bei Windows) und lade ein kompaktes Modell herunter:
   ```
   ollama pull llama3.2
   ```
   *(Alternative: `ollama pull phi4-mini` — beide sind klein genug für normale Laptops. Llama 3.2 ist aber die bessere Wahl, weil es strukturierte Ausgaben — z. B. das OKF-Frontmatter in Kapitel 5 — zuverlässiger einhält als Phi-4-mini.)*
4. Der Download ist etwa 2–3 GB groß — je nach Internetverbindung dauert das ein paar Minuten. Am besten schon zu Beginn der Session anstoßen und nebenbei mit den anderen Schritten weitermachen, während er im Hintergrund läuft.
5. Test, ob es funktioniert: `ollama run llama3.2` — du solltest direkt im Terminal mit dem Modell chatten können. Mit `/bye` beendest du den Test wieder.

**Voraussetzungen:** mindestens 8 GB RAM (16 GB komfortabler), ca. 4 GB freier Speicherplatz für Ollama selbst plus das Modell. Eine Grafikkarte ist nicht nötig, macht die Antworten aber schneller.

*Hinweis zur Erwartungshaltung: Ein kleines lokales Modell ist spürbar schwächer als Claude oder ChatGPT im Browser — für „live sehen, wie die Integration in Obsidian funktioniert" reicht es aber gut aus.*

## Schritt 6b: Obsidian mit Ollama verbinden

Jetzt verbindest du das gerade installierte Ollama mit Obsidian:

1. Einstellungen → **Externe Erweiterungen** → **Durchsuchen**
2. Installiere **„Copilot"** (oder alternativ „Text Generator") und aktiviere es

⚠️ **Namensfalle:** Dieses Obsidian-Plugin heißt zufällig auch „Copilot" — hat aber nichts mit GitHub Copilot oder Microsoft 365 Copilot zu tun. Reiner Zufall bei der Namensgebung.

3. In den Plugin-Einstellungen: Provider auf **Ollama** stellen, Modell `llama3.2` auswählen — läuft lokal auf `localhost`, keine weiteren Zugangsdaten nötig

## Schritt 7 (optional): Claude-API-Key einrichten

*Nur für alle, die statt Ollama (oder zusätzlich dazu) direkt mit Claude arbeiten möchten und keine Kosten scheuen.*

Wichtig: Das ist **nicht dasselbe** wie ein claude.ai-Abo — die API wird separat abgerechnet (Pay-as-you-go), auch wenn du bereits ein Abo hast.

1. **console.anthropic.com** öffnen und einloggen/registrieren (E-Mail oder Google-Konto)
2. Unter **Billing** eine Zahlungsmethode hinterlegen und Guthaben aufladen — 5 $ reichen zum Start
3. Zu **API Keys** navigieren, auf **Create Key** klicken, dem Key einen Namen geben (z. B. „Obsidian")
4. Den Key **sofort kopieren** — er wird nur einmal angezeigt und beginnt mit `sk-ant-api03-…`
5. *Optional, aber empfohlen:* direkt ein Ausgabenlimit setzen

Den Key brauchst du erst in Kapitel 5, wenn du dort im Plugin von Ollama auf Claude umschaltest — für jetzt reicht es, ihn sicher gespeichert zu haben (z. B. in einem Passwort-Manager).

## Offene Punkte / noch zu ergänzen

- [ ] Screenshots für Download-Button und „Open folder as vault"
- [ ] Hinweise für typische Stolperfallen (z. B. Sicherheitswarnung beim ersten Öffnen, falsche ZIP-Entpackung)
- [ ] Kurzer Check am Ende: „Siehst du die Ordnerstruktur links? Dann ist alles bereit."
- [ ] Sicherstellen, dass die 5 Beispiel-Notizen im tatsächlichen Vault-Download enthalten sind
- [ ] Screenshot für Community-Plugin-Suche/Installation
- [ ] Screenshot/GIF, wie die drei Windows-Terminals (cmd/PowerShell/Windows Terminal) sich optisch unterscheiden
- [ ] Testen, ob llama3.2 (bzw. phi4-mini als Alternative) auf typischer Workshop-Hardware (älteres Windows-Notebook, 8 GB RAM) noch flüssig läuft
- [ ] Prüfen, ob Ollama-Download+Chat-Test realistisch in die Session-Zeit passt, oder ob Zeitpuffer eingeplant werden muss
