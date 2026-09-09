# Installation Bonus: Power-Usecase, Command Line, Git

Alle drei Teile sind optional — nur nötig, wenn du das jeweilige Bonus-Kapitel machen willst. Pflichtteil (Teil A + B) steht in [[00-installation]].

---

# Teil C: Vor dem Bonus-Kapitel Power-Usecase (optional)

## Schritt 8: Kern-Plugins prüfen

Templates, Basen und Canvas sind **schon in Obsidian eingebaut** — nur prüfen, ob sie an sind:

Öffne **Einstellungen** → **Obsidian-Erweiterungen**, Schalter bei diesen dreien an:

| Kern-Plugin | Wofür |
| --- | --- |
| **Vorlagen** | Vorlagen mit fertigem OKF-Frontmatter-Gerüst |
| **Basen** | Datenbank-artige Ansichten ohne Abfragesprache |
| **Canvas** | Unendliches Whiteboard |

*Schnellcheck: Befehlspalette (`Strg/Cmd + P`), Namen tippen — erscheinen Befehle, ist's aktiv.*

*Taucht **Basen** gar nicht auf: Obsidian-Version zu alt, unter Einstellungen → **Über** aktualisieren.*

## Schritt 9: Cron installieren (optional)

Wie Claudian installieren (Einstellungen → Externe Erweiterungen → Durchsuchen → „Cron" → Installieren → Aktivieren). Dient im Bonus-Kapitel nur als Ausblick, keine Pflichtübung — Installation kann auch entfallen.

**Weiter geht's:** Auf zu [[1-power-usecase|Bonus-Kapitel Power-Usecase]].

---

# Teil D: Vor dem Bonus-Kapitel Command Line (optional)

## Schritt 10: Ein besseres Windows-Terminal

*Nur Windows.*

**Empfohlen:** **[Git for Windows](https://git-scm.com/downloads)** — bringt **Git Bash** mit (echte Unix-Befehle: `grep`, `sort`, `wc`, `uniq`), deckt gleichzeitig Teil E ab. Ohne Git Bash brauchst du im Bonus-Kapitel PowerShell-Alternativen, manche Befehle gibt's in cmd gar nicht.

Optional zusätzlich: **Windows Terminal** aus dem Microsoft Store (bündelt cmd/PowerShell/Git Bash mit Tabs).

**Keine Adminrechte?** [[Ohne Adminrechte]] — kurz gesagt: bei PowerShell bleiben, das Bonus-Kapitel hat Alternativen zu jedem Unix-Befehl.

## Schritt 11: Werkzeuge für die Spaß-Übungen

Rein optional:

| Werkzeug | Mac/Linux | Windows |
| --- | --- | --- |
| **cowsay** | `brew install cowsay` / `sudo apt install cowsay` | `Install-Module -Name CowsaySharp -Scope CurrentUser` |
| **ImageMagick** | `brew install imagemagick` / `sudo apt install imagemagick` | Installer von [imagemagick.org](https://imagemagick.org/script/download.php) |

**Keine Adminrechte?** Beide gehen auch ohne — siehe [[Ohne Adminrechte]]. Blockt die IT auch das: kein Problem, rein optional.

**Weiter geht's:** Auf zu [[1-command-line|Bonus-Kapitel Command Line]].

---

# Teil E: Vor dem Bonus-Kapitel Git (optional)

## Schritt 12: Git installieren

- **Windows:** [Git for Windows](https://git-scm.com/downloads) — in Schritt 10 schon installiert? Dann fertig.
- **macOS:**
  ```
  git --version
  ```
  (Git fehlt? macOS bietet die Installation direkt an)
- **Linux:**
  ```
  sudo apt install git
  ```

Test:
```
git --version
```

*Keine Adminrechte? [[Ohne Adminrechte]] für eine portable Variante ganz ohne Installation.*

## Schritt 13: GitHub-Konto anlegen

1. [github.com](https://github.com) → **Sign up**
2. E-Mail, Benutzername, Passwort (Passwort-Manager)
3. E-Mail bestätigen

*Konto schon da? Nichts zu tun. Anmeldung beim ersten `git push` klärt das Bonus-Kapitel Git — das normale Passwort funktioniert dafür nicht.*

## Schritt 14: Erweiterung „Obsidian Git" installieren

Einstellungen → **Externe Erweiterungen** → **Durchsuchen** → **„Obsidian Git"** → installieren, aktivieren.

*Die Einrichtung läuft im Kapitel trotzdem einmal von Hand durch — bevor ein Knopf sie übernimmt.*

**Weiter geht's:** Auf zu [[1-git|Bonus-Kapitel Git]].
