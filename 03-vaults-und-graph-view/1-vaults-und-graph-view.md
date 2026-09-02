# Vaults & Graph-Ansicht

Im Ordner **`notizen/`** liegen bereits fertige Notizen in deinem Vault. Fünf davon (`Obsidian.md`, `Zettelkasten.md`, `Second Brain.md`, `OKF.md`, `KI-Workflow.md`) sind noch fast unverlinkt — diese Verbindungen baust du in diesem Kapitel selbst auf.

*Eine Verbindung ist als Vorlage schon da: Ganz unten in `Zettelkasten.md` steht `Baut die Grundlage für das Prinzip des [[Second Brain]].` Schau sie dir kurz an — so sieht ein Link im Rohtext aus, und genauso legst du gleich deine eigenen an.*

*Der Ordner liegt bewusst außerhalb der Kapitel-Ordner: Die Notizen erklären Begriffe, auf die aus mehreren Kapiteln heraus verlinkt wird, und dienen später auch als Material für Bases, Canvas und die KI-Übungen.*

*`Kundenprojekt-Lotos.md` bleibt hier bewusst unverlinkt und taucht als isolierter Punkt in der Graph-Ansicht auf — kein Fehler, sie wird erst in Kapitel 4 gebraucht.*

## Kurzer Zwischenstopp: Was ist Frontmatter?

Öffne `Obsidian.md` — ganz oben siehst du einen Block zwischen zwei `---`-Linien mit `type: Tool` drin. Das nennt man [[Frontmatter]] — die verlinkte Beispiel-Notiz erklärt es kurz. Sie ist übrigens gleich dein erstes Beispiel dafür, wie Verlinkung in diesem Vault funktioniert.

## 1. Was ist ein Vault

Ein Vault ist einfach ein Ordner auf der Festplatte, den Obsidian als „Notiz-Sammlung" erkennt — der Ordner, den du bei der Installation schon heruntergeladen und geöffnet hast. Keine Cloud, keine Magie dahinter.

**Übung:** Öffne die Vault-Einstellungen und schau, welcher Pfad dahinter liegt.

## 2. Verlinkung mit [[doppelten eckigen Klammern]]

Tippst du `[[`, schlägt Obsidian automatisch bestehende Notizen zum Verlinken vor. Verlinkst du eine Notiz, die noch nicht existiert, legt Obsidian sie automatisch an.

**Übung:** In `Zettelkasten.md` findest du bereits einen fertigen Link zu `Second Brain.md` als Beispiel, wie das aussehen soll. Verlinke die restlichen Notizen gemäß dieser Vorgabe:

- `Obsidian.md` → `Zettelkasten.md`, `Second Brain.md`
- ~~`Zettelkasten.md` → `Second Brain.md`~~ *(schon vorhanden — als Beispiel)*
- `Second Brain.md` → `OKF.md`
- `OKF.md` → `Obsidian.md` (Rückverlinkung!)
- `KI-Workflow.md` → `OKF.md`, `Obsidian.md`

## 3. Graph-Ansicht

Die Graph-Ansicht zeigt alle Notizen als Punkte, Verlinkungen als Linien dazwischen. Du öffnest sie über das Netz-Symbol in der Seitenleiste.

**Übung:** Öffne die Graph-Ansicht. Findest du den Cluster aus den fünf Notizen? Welche Notiz hat die meisten Verbindungen?

## 4. Rückverweise-Panel

Unten in jeder Notiz zeigt Obsidian an, wer *auf diese Notiz* verlinkt — das ist die Kehrseite des Graphen, nur als Liste statt als Bild.

**Übung:** Öffne `Obsidian.md` und schau ins Rückverweise-Panel. Wer verlinkt hierher?

---

## Auflösungen

3. **Graph-Ansicht:** Unter den fünf Beispiel-Notizen ist `Obsidian.md` am stärksten vernetzt — 2 ausgehende Links (zu Zettelkasten, Second Brain) plus 2 eingehende Links (von OKF, KI-Workflow) ergeben 4 Verbindungen. *Nebenbei fällt dir vielleicht auf, dass auch die Kapitel-Notizen selbst im Graphen auftauchen und z. B. auf [[Frontmatter]] verlinken — das Workshop-Material ist selbst ein kleines Second Brain.*

4. **Rückverweise-Panel:** In `Obsidian.md` zeigt das Rückverweise-Panel `OKF.md` und `KI-Workflow.md` — das sind die beiden Notizen, die auf `Obsidian.md` verlinken.
