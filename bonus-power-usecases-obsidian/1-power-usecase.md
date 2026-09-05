# Bonus: Power-Usecase — dieselbe Idee, jetzt in Obsidian selbst

## Einstieg: Dieselbe Idee, diesmal ohne KI

In Kapitel 4 hast du deinem Vault Fragen gestellt — zuletzt auch eine, die im Grunde eine Datenbank-Abfrage war: „Zeig mir alle Notizen mit `type: Projekt`, die noch `status: draft` sind."

Für genau solche Fragen braucht es nicht zwingend eine KI. Obsidian bringt dafür eigene Werkzeuge mit, und der Unterschied zur KI ist: Das Ergebnis bleibt stehen — als Ansicht, die sich bei jeder neuen Notiz von selbst aktualisiert, statt als Antwort, die du jedes Mal neu erfragst.

## Rahmenerzählung

Stell dir vor, die fünf Notizen aus dem Ordner `notizen/` (`Obsidian`, `Zettelkasten`, `Second Brain`, `OKF`, `KI-Workflow`) sind Teil der Wissensbasis einer Solo-Beraterin. Sie nutzt sie, um Konzepte für Kundinnen nachzuschlagen und wiederzuverwenden.

## Feature 1: Templates — Konsistenz durch Vorlagen pro Notiz-Typ

**Templates** ist ein Kern-Plugin (keine Installation nötig, ggf. nur unter Einstellungen → Obsidian-Erweiterungen einschalten). Es fügt einen vordefinierten Textbaustein in eine Notiz ein — und beherrscht dabei auch schon dynamische Werte: `{{title}}`, `{{date}}` und `{{time}}`, auf Wunsch mit eigenem Format wie `{{date:YYYY-MM-DD}}`.

Der eigentliche Kniff für ein wachsendes Second Brain: pro `type` ein eigenes Template. Eine Notiz vom Typ „Kundenprojekt" bekommt immer dieselben Frontmatter-Felder vorgegeben (z. B. `type`, `status`, `ansprechpartnerin`, `kickoff`), eine Notiz vom Typ „SOP" andere. Über die Befehlspalette (`Cmd/Ctrl+P`) rufst du „Vorlage einfügen" auf, wählst den Typ — und das Frontmatter-Gerüst steht, ohne dass du es jedes Mal neu tippen musst.

*Einmalig nötig: Unter Einstellungen → **Templates** einen Ordner für deine Vorlagen festlegen, z. B. `templates/`.*

**So sieht das in der Praxis aus:** Ein Template namens „Neues Konzept" gibt `type`, `status` und `sources` leer vor und setzt `created` automatisch auf `{{date}}`. Jede neue Konzept-Notiz startet damit strukturell gleich — genau das Frontmatter, das die KI in Kapitel 4 braucht, steht schon, bevor du den ersten Satz Text schreibst.

*Ausblick: Wenn du Templates ausreizt, ist das Community-Plugin **Templater** der nächste Schritt — es kann beim Anlegen nach Werten fragen („Wie heißt die Kundin?"), den Dateinamen setzen, die Notiz automatisch in den richtigen Ordner verschieben und kleine Skripte ausführen.*

## Feature 2: Den ganzen Kreislauf automatisieren

Templates lösen die Konsistenz beim *Anlegen* einer Notiz. Was aber, wenn du den ganzen Second-Brain-Kreislauf aus Kapitel 4 — reinwerfen, verdichten, verlinken, wiederfinden — nicht mehr einzeln anstoßen willst, sondern als festen Ablauf?

Genau das hat Tom Liu gebaut, aufbauend auf Andrej Karpathys Idee aus Kapitel 4: ein wiederverwendbares Regelwerk für Claude Code, das jede neue Quelle automatisch nach demselben Muster verarbeitet — einlesen, zu Wiki-Seiten verdichten, bei Fragen mit Quellenangaben antworten, und in Abständen die Qualität des ganzen Wikis prüfen.[^1]

Der entscheidende Unterschied zu den Prompts aus Kapitel 4: Dort hast du Claudian jedes Mal einzeln gesagt, was zu tun ist. Ein solches Regelwerk hält diese Anweisungen einmal fest — als Datei, nicht als wiederholter Prompt — und macht sie so für jede neue Notiz automatisch anwendbar.

*Nichts zum Nachmachen in diesem Workshop, aber ein guter Fingerzeig, wohin die Reise geht, wenn dir manuelles Prompten pro Notiz irgendwann zu mühsam wird: Der Clip dazu liegt unter `Clippings/` und ist über eine Multi-Hop-Frage erreichbar, genau wie in Kapitel 4 geübt.*

## Feature 3 (Ausblick, ohne Übung): Cron

Es gibt eine Externe Erweiterung namens **„Cron"** (`obsidian-cron`), das Obsidian-Befehle oder eigene Skripte nach echter Cron-Syntax zeitgesteuert ausführt — solange Obsidian offen bzw. im Hintergrund läuft.

**Business-Beispiel:** Ein wöchentlicher Job, der veraltete Notizen findet (mehr dazu, wie man „veraltet" sauber definiert, in Kapitel 4, Teil 5) und automatisch auf `status: draft` zurücksetzt oder eine Erinnerungs-Notiz erzeugt — „diese [[SOP]]s müssen überprüft werden."

## Das kann Obsidian auch: Bases und Canvas

Zwei weitere native Bordmittel, kurz erwähnt — kein Muss, aber gut zu wissen, dass es sie gibt:

- **Bases** filtert und sortiert Notizen nach Frontmatter-Feldern und zeigt sie als Tabelle — eine kleine Datenbank-Ansicht ganz ohne Plugin. Fertiges Beispiel zum Anschauen: `notizen/beispiel-base.base`.
- **Canvas** ist ein unendliches Whiteboard: Notizen, Text-Karten und Bilder frei platzieren und mit Pfeilen verbinden. Anders als die Graph-Ansicht (automatisch aus Links berechnet) ist Canvas manuell und räumlich — gut für Brainstorming oder um einen Workflow zu skizzieren. Fertiges Beispiel: `notizen/beispiel-canvas.canvas` — dieselben fünf Notizen wie in der Graph-Ansicht aus Kapitel 3, nur räumlich statt automatisch angeordnet, plus eine Kommentar-Karte.

---

*Einige Ideen in diesem Bonus-Kapitel (Templates pro Notiz-Typ, Bases statt Dataview für Datenbank-Ansichten) sind inspiriert durch: Bruno Paz, „How I use Obsidian to take notes and manage all my knowledge", brunopaz.dev, 5. Februar 2026. [brunopaz.dev/blog/how-i-use-obsidian-to-take-notes-and-manage-all-my-knowledge](https://brunopaz.dev/blog/how-i-use-obsidian-to-take-notes-and-manage-all-my-knowledge/)*

[^1]: Tom Liu, „Building Your Second Brain using Claude Code and Obsidian — Part 1", Medium, 6. Mai 2026. Liegt als Beispiel-Clip in `Clippings/`.
