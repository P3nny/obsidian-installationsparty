# Vaults & Graph-Ansicht

Die fünf Beispiel-Notizen (`Obsidian.md`, `Zettelkasten.md`, `Second Brain.md`, `OKF.md`, `KI-Workflow.md`) liegen bereits fertig in deinem Vault — nur noch ohne Verlinkung. Die baust du in diesem Kapitel selbst auf.

*Eine sechste Notiz, `Kundenprojekt-Lotos.md`, liegt ebenfalls schon im Vault, bleibt hier aber bewusst unverlinkt und taucht als isolierter Punkt in der Graph-Ansicht auf — kein Fehler, sie wird erst in Kapitel 6 gebraucht.*

## 1. Was ist ein Vault

Ein Vault ist einfach ein Ordner auf der Festplatte, den Obsidian als „Notiz-Sammlung" erkennt — der Ordner, den du in der Vorbereitung schon heruntergeladen und geöffnet hast. Keine Cloud, keine Magie dahinter.

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

3. **Graph-Ansicht:** `Obsidian.md` ist am stärksten vernetzt — 2 ausgehende Links (zu Zettelkasten, Second Brain) plus 2 eingehende Links (von OKF, KI-Workflow) ergeben 4 Verbindungen insgesamt. Alle anderen Notizen kommen auf höchstens 3.

4. **Rückverweise-Panel:** In `Obsidian.md` zeigt das Rückverweise-Panel `OKF.md` und `KI-Workflow.md` — das sind die beiden Notizen, die auf `Obsidian.md` verlinken.
