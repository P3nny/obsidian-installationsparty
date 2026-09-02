# Vaults & Graph-Ansicht

Im Ordner **`notizen/`** liegen bereits fertige Notizen in deinem Vault. Fünf davon (`Obsidian.md`, `Zettelkasten.md`, `Second Brain.md`, `OKF.md`, `KI-Workflow.md`) sind schon teilweise untereinander verlinkt — die letzten drei Verbindungen baust du in diesem Kapitel selbst auf.

*So sieht ein Link im Rohtext aus: Ganz unten in `Zettelkasten.md` steht `Baut die Grundlage für das Prinzip des [[Second Brain]].` Schau ihn dir kurz an — genauso legst du gleich deine eigenen an.*

*Der Ordner liegt bewusst außerhalb der Kapitel-Ordner: Die Notizen erklären Begriffe, auf die aus mehreren Kapiteln heraus verlinkt wird, und dienen später auch als Material für Bases, Canvas und die KI-Übungen.*

## Kurzer Zwischenstopp: Was ist Frontmatter?

Wenn Du  `strg` gedrückt hälst und dann auf einen Links klickst, öffnet ihn Obsidian in einem zweiten Tab. Öffne die Notiz [[Obsidian]] als zweiten Tab — ganz oben siehst du einen Block zwischen zwei `---`-Linien mit `type: Tool` drin. Das nennt man [[Frontmatter]] — die verlinkte Beispiel-Notiz erklärt es kurz. Sie ist übrigens gleich dein erstes Beispiel dafür, wie Verlinkung in diesem Vault funktioniert.

## 1. Was ist ein Vault

Ein Vault ist einfach ein Ordner auf der Festplatte, den Obsidian als „Notiz-Sammlung" erkennt — der Ordner, den du bei der Installation schon heruntergeladen und geöffnet hast. Keine Cloud, keine Magie dahinter.

## 2. `Verlinkung mit [[doppelten eckigen Klammern]]`

Tippst du `[[`, schlägt Obsidian automatisch bestehende Notizen zum Verlinken vor. Verlinkst du eine Notiz, die noch nicht existiert, legt Obsidian sie automatisch an.

**Übung:** Die meisten Notizen sind schon untereinander verlinkt (`Zettelkasten.md` → `Second Brain.md` → `OKF.md` → `Obsidian.md`). Es fehlen genau drei Links — die setzt du selbst:

- `Obsidian.md` → `Zettelkasten.md` und `Second Brain.md` (zwei Links in einem Satz)
- `KI-Workflow.md` → `Obsidian.md` (Rückverlinkung!)

Schreib die Links in einen ganzen Satz, nicht als nackte Klammern — z. B. „Baut auf der Methode des [[Zettelkasten]] auf."

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
