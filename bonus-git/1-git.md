# Bonus: Git

*Voraussetzung: Git ist installiert ([[00-installation#Teil E: Vor dem Bonus-Kapitel Git (optional)|Installation, Teil E]]). Die Grundlagen aus dem Bonus-Kapitel Command Line helfen, sind aber kein Muss — jeder Befehl steht hier zum Kopieren.*

## Was ist Git — und warum kennt es jede Entwicklerin?

Stell dir vor, du spielst ein Videospiel: Ohne Speicherpunkt heißt ein Fehlschlag beim Endboss „das ganze Level nochmal", mit Speicherpunkt nur „zurück zur letzten guten Stelle". **Genau das macht [[Git]] für deine Dateien** — nur dass du zu jedem früheren Stand zurück kannst, nicht nur zum letzten. Details und die Begründung, warum das in der Softwareentwicklung praktisch alternativlos ist, stehen in der verlinkten Notiz; hier geht's direkt in die Praxis.

Für deinen Vault ist vor allem der Speicherpunkt-Aspekt interessant, und ganz nebenbei bekommst du Sync zwischen zwei Geräten dazu (siehe Kapitel 2).

**Drei Begriffe reichen für den Anfang:**

| Begriff       | Im Videospiel-Bild                                        |
| ------------- | --------------------------------------------------------- |
| **[[Repository]]** | Das Spiel samt allen Speicherständen — bei dir: dein Vault |
| **[[Commit]]**    | Speichern. Du machst einen Speicherpunkt mit Notizzettel dran: „Was habe ich gerade geändert?" |
| **Push**      | Den Speicherstand zusätzlich ins Netz hochladen — sicher vor Laptop-Verlust, abrufbar auf dem zweiten Gerät |

## Schritt 1: GitHub-Konto anlegen

Git läuft auf deinem Rechner. **GitHub** ist ein Dienst im Netz, auf den du deine Speicherstände hochladen kannst — der bekannteste von mehreren (Alternativen: GitLab, Codeberg). Für `push` brauchst du dort ein Konto.

1. [github.com](https://github.com) aufrufen, **Sign up**
2. Mit E-Mail-Adresse registrieren, Benutzernamen wählen
3. Passwort in deinem Passwort-Manager speichern
4. E-Mail-Adresse bestätigen

*Ein kostenloses Konto reicht vollständig aus, auch für private Repositories.*

## Schritt 2: Git einmalig einrichten

Git schreibt an jeden Commit, von wem er stammt. Das musst du einmal pro Rechner hinterlegen — sonst verweigert Git den ersten Commit:

```
git config --global user.name "Dein Name"
git config --global user.email "deine@email.de"
```

Nimm dieselbe E-Mail-Adresse wie bei GitHub, dann werden deine Commits dort auch dir zugeordnet.

## Schritt 3: Aus deinem Vault ein Repository machen

Falls du das Workshop-Material als **ZIP heruntergeladen** hast (so wie in [[00-installation#Teil A: Basis — vor Kapitel 1|Teil A]] beschrieben), ist dein Ordner noch **kein** Repository — die ZIP-Datei enthält keine Git-Daten. Das holst du jetzt nach.

Öffne ein Terminal in deinem Vault-Ordner und tippe:

```
git init
```

**Erwartung:** Git antwortet mit `Initialized empty Git repository in …`. Ab jetzt existiert in deinem Vault ein unsichtbarer Unterordner `.git` — dort landen alle Speicherstände. Wenn du ihn löschst, ist der Verlauf weg; ansonsten musst du dich nie darum kümmern.

*(Wer das Material stattdessen mit `git clone` geholt hat, überspringt diesen Schritt — dann ist bereits ein Repository da.)*

## Schritt 4: Eine `.gitignore` anlegen

Nicht alles im Vault soll gespeichert werden. Obsidian schreibt in `.obsidian/workspace.json` mit, welche Notiz gerade offen ist und wie deine Fenster angeordnet sind — das ändert sich ständig und würde jeden Commit mit sinnlosem Rauschen füllen. Auf zwei Geräten produziert es zuverlässig Konflikte.

Lege dafür im Vault-Hauptordner eine Datei namens `.gitignore` an (der Punkt am Anfang gehört dazu!) mit diesem Inhalt:

```
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.trash/
.DS_Store
```

Du kannst die Datei direkt in Obsidian anlegen. Die restlichen `.obsidian`-Dateien lässt du bewusst drin — so wandern deine Einstellungen und Plugin-Konfigurationen mit auf das zweite Gerät.

## Schritt 5: Der erste Commit

Zwei Befehle, und dein erster Speicherpunkt steht:

```
git add .
git commit -m ":tada: Mein Vault, erster Stand"
```

- `git add .` sagt: „Alles, was sich geändert hat, kommt in den nächsten Speicherpunkt." (Der Punkt bedeutet „alles hier".)
- `git commit -m "…"` legt den Speicherpunkt an. Der Text hinter `-m` ist dein Notizzettel — schreib etwas, das dir in drei Monaten noch etwas sagt.

**Erwartung:** Git meldet eine Zeile wie `12 files changed, 340 insertions(+)`.

Jederzeit nachschauen, was gerade ungespeichert ist:

```
git status
```

## Schritt 6: Ein Repository auf GitHub anlegen

1. Auf [github.com](https://github.com) oben rechts auf **+** → **New repository**
2. Namen vergeben, z. B. `mein-vault`
3. **Private** auswählen, wenn deine Notizen privat bleiben sollen (das ist bei einem Second Brain fast immer der Fall)
4. ⚠️ **Wichtig: Keine der Optionen „Add a README file", „Add .gitignore" oder „Choose a license" anhaken.** Das Repository muss komplett leer bleiben.

> **Warum das wichtig ist:** Hakst du eine dieser Optionen an, legt GitHub bereits selbst einen Commit an. Dein Rechner und GitHub haben dann zwei unterschiedliche Verläufe, die nichts voneinander wissen — und dein erster `push` wird mit `rejected (non-fast-forward)` abgelehnt. Das ist die häufigste Stolperfalle überhaupt beim ersten eigenen Repository.

Nach dem Anlegen zeigt GitHub dir eine Seite mit Befehlen. Die Adresse, die du brauchst, sieht so aus: `https://github.com/DEINNAME/mein-vault.git`

## Schritt 7: Der erste Push

```
git branch -M main
git remote add origin https://github.com/DEINNAME/mein-vault.git
git push -u origin main
```

- `git branch -M main` benennt deinen Hauptzweig einheitlich `main` (GitHub erwartet das so)
- `git remote add origin …` merkt sich, wohin hochgeladen wird. `origin` ist einfach der übliche Spitzname dafür
- `git push -u origin main` lädt hoch

### Was jetzt bei der Anmeldung passiert

Hier hakt es bei den meisten zum ersten Mal. Wichtig zu wissen: **GitHub akzeptiert seit 2021 kein Konto-Passwort mehr** für diesen Weg. Fragt Git nach einem Passwort und du tippst dein GitHub-Passwort ein, wird es abgelehnt — das ist kein Fehler von dir.

| Dein System        | Was passiert / was du tust                                                                                                                |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Windows**        | Es öffnet sich automatisch ein Browserfenster. Einmal **Authorize** klicken — fertig. Der **Git Credential Manager** ist in Git for Windows enthalten und merkt sich die Anmeldung dauerhaft. Du musst nichts vorbereiten. |
| **macOS / Linux**  | Vorher einmal die GitHub-CLI einrichten: `gh auth login` → **HTTPS** wählen → Browser-Login. Danach funktioniert `git push` ohne Nachfrage. (GitHub CLI installieren: `brew install gh` bzw. `sudo apt install gh`) |
| **Notfall**        | Wenn der Browser-Login blockiert ist (Firmenrechner): siehe Kasten unten                                                                    |

Beide Wege kommen auch mit Zwei-Faktor-Authentifizierung zurecht.

> **Notfall-Variante: Personal Access Token (PAT)**
> Wenn der Browser-Weg nicht geht, erzeugst du dir ein Ersatz-Passwort für Git:
> 1. GitHub → Profilbild → **Settings** → ganz unten **Developer settings**
> 2. **Personal access tokens** → **Tokens (classic)** → **Generate new token (classic)**
> 3. Häkchen bei **repo** setzen, Laufzeit wählen, erzeugen
> 4. Token **sofort kopieren** — er wird nur ein einziges Mal angezeigt
> 5. Beim `git push` als **Passwort** einfügen (Benutzername = dein GitHub-Name)
>
> Der Token ist kein Passwort-Ersatz für die Webseite, sondern nur für Git. Behandle ihn trotzdem wie ein Passwort.

**Erwartung:** Nach erfolgreichem Push steht dein Vault auf GitHub. Lade die Repository-Seite im Browser neu — deine Notizen sind da.

## Schritt 8: Ab jetzt ohne Terminal — das Plugin „Obsidian Git"

Den Ablauf einmal von Hand gemacht zu haben, lohnt sich: Du weißt jetzt, was passiert. Im Alltag willst du dafür aber kein Terminal mehr öffnen — dafür gibt es eine Externe Erweiterung.

1. **Einstellungen** → **Externe Erweiterungen** → **Durchsuchen**
2. Nach **„Obsidian Git"** suchen, installieren, aktivieren

Das Plugin nutzt das Git, das du in [[00-installation#Teil E: Vor dem Bonus-Kapitel Git (optional)|Teil E]] installiert hast, und die Anmeldung aus Schritt 7 — es ist also sofort einsatzbereit. Was es dir abnimmt:

| Funktion                     | Was sie tut                                                              |
| ---------------------------- | ------------------------------------------------------------------------ |
| **Commit-and-sync**          | Ein Befehl in der Befehlspalette (`Strg/Cmd + P`) macht Commit und Push in einem |
| **Automatisch im Intervall** | Speichert und lädt hoch, z. B. alle 10 Minuten — ganz ohne dein Zutun     |
| **Beim Start pullen**        | Holt sich beim Öffnen von Obsidian den Stand vom anderen Gerät            |
| **Verlaufs-Ansicht**         | Zeigt deine Speicherpunkte in der Seitenleiste, inklusive Zeilenvergleich |

**Mini-Übung:** Ändere eine beliebige Notiz. Öffne die Befehlspalette, tippe „commit" und führe **Commit-and-sync** aus. Schau danach im Browser auf GitHub nach — die Änderung ist dort.

*Hinweis zu Mobilgeräten: Das Plugin läuft auch auf Handy und Tablet, ist dort aber ausdrücklich als instabil gekennzeichnet und kann bei großen Vaults an Speichergrenzen stoßen. Für den Anfang: erstmal am Rechner bleiben.*

## Was du damit gewonnen hast

- Einen **Speicherpunkt-Verlauf** für deinen gesamten Vault
- Ein **Backup** außerhalb deines Laptops
- **Sync** zwischen zwei Geräten, ohne einen kostenpflichtigen Dienst (Option 3 aus Kapitel 2)

Wenn du tiefer einsteigen willst, sind `git log` (alle Speicherpunkte ansehen), `git diff` (was habe ich geändert?) und `git restore` (zurück zum letzten Stand) die nächsten drei Befehle, die sich lohnen — alle im [[2-cheatsheet-git|Git Cheatsheet]] zum Nachschlagen.

---

## Offene Punkte / noch zu ergänzen

- [ ] Screenshots: „New repository"-Formular mit den nicht angehakten Optionen, Browser-Fenster des Git Credential Manager
- [ ] Prüfen, ob `gh` auf typischen Mac-Teilnehmerinnen-Rechnern ohne Homebrew verfügbar ist; ggf. PAT-Variante nach vorne ziehen
- [ ] Merge-Konflikte: bewusst ausgelassen — entscheiden, ob ein kurzer Absatz „was tun, wenn zwei Geräte dasselbe geändert haben" nötig ist

*Aufbau und didaktischer Ablauf dieses Kapitels orientieren sich am Tutorial von [[Django Girls]] (CC BY-SA 4.0), das Git ebenfalls über `init` → `add` → `commit` → `push` einführt: [tutorial.djangogirls.org/en/deploy](https://tutorial.djangogirls.org/en/deploy/)*
