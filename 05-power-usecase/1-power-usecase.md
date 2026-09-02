# Power-Usecase: Dieselbe Idee, jetzt in Obsidian selbst

## Einstieg: Von der KI im Terminal zur KI in Obsidian

Im letzten Kapitel hast du erlebt, wie deine KI dir einen exakten Terminal-Befehl geschrieben hat, statt dass du die Syntax selbst kennen musstest — du beschreibst in normaler Sprache, was du willst, die KI übersetzt es in die formale Sprache, die der Computer versteht.

Genau dasselbe Prinzip steckt auch in den Obsidian-eigenen Power-Features dieses Kapitels: Statt eine neue Abfragesprache zu lernen, beschreibst du, was du sehen willst, und das Feature erledigt den Rest — mal durch die KI, mal durch eine simple Klick-Oberfläche, die dieselbe Idee ganz ohne KI umsetzt.

## Rahmenerzählung

Stell dir vor, die fünf Notizen aus dem Ordner `notizen/` (`Obsidian`, `Zettelkasten`, `Second Brain`, `OKF`, `KI-Workflow`) sind Teil der Wissensbasis einer Solo-Beraterin. Sie nutzt sie, um Konzepte für Kundinnen nachzuschlagen und wiederzuverwenden — will aber auf einen Blick sehen, welche Notizen noch unfertig sind, bevor sie in ein Angebot einfließen.

## Feature 1: Bases — Datenbank-Ansichten ohne Abfragesprache

**Bases** ist eine in Obsidian eingebaute Funktion (kein Plugin, keine Installation nötig), mit der du Notizen nach [[Frontmatter]]-Feldern filtern, sortieren und als Tabelle anzeigen kannst — komplett über Klick-Oberfläche, ganz ohne eigene Abfragesprache zu lernen.

**Übung:**
1. Ergänze bei diesen fünf Notizen ein `status`-Feld im Frontmatter (`draft` oder `stable`) — frei nach eigener Einschätzung.
2. Erstelle eine neue Base, filtere auf `status = draft`.
3. Erweitere die Ansicht um eine zweite Spalte: `type` neben `status`.

**Business-Bogen:** Genau so eine Ansicht lässt sich zu einem kleinen Dashboard ausbauen — „Alle Notizen, die vor einem Kundentermin noch geprüft werden müssen." Das ist der Punkt, an dem Obsidian vom reinen Notizzettel zum echten Wissens-Werkzeug wird, ganz ohne dass du dafür programmieren musst.

## Feature 2: Canvas

Obsidians eingebautes „unendliches Whiteboard": Notizen, Text-Karten, Bilder oder Web-Links frei auf einer 2D-Fläche platzieren und händisch mit Pfeilen verbinden. Anders als der Graph View (automatisch aus Links berechnet) ist Canvas manuell und räumlich — gut für Brainstorming oder um einen Workflow zu skizzieren.

**Mini-Übung:** Lege ein Canvas an, ziehe die fünf Notizen aus `notizen/` als Karten hinein und ergänze eine Freitext-Karte mit einem Kommentar — z. B. so, wie du das eigene Wissenssystem einer Kundin präsentieren würdest.

## Feature 3: Templates — Konsistenz durch Vorlagen pro Notiz-Typ

**Templates** ist ein Kern-Plugin (keine Installation nötig, ggf. nur unter Einstellungen → Obsidian-Erweiterungen einschalten). Es fügt einen vordefinierten Textbaustein in eine Notiz ein — und beherrscht dabei auch schon dynamische Werte: `{{title}}`, `{{date}}` und `{{time}}`, auf Wunsch mit eigenem Format wie `{{date:YYYY-MM-DD}}`.

Der eigentliche Kniff für ein wachsendes Second Brain: pro `type` ein eigenes Template. Eine Notiz vom Typ „Kundenprojekt" bekommt immer dieselben Frontmatter-Felder vorgegeben (z. B. `type`, `status`, `ansprechpartnerin`, `kickoff`), eine Notiz vom Typ „SOP" andere. Über die Befehlspalette (`Cmd/Ctrl+P`) rufst du „Vorlage einfügen" auf, wählst den Typ — und das Frontmatter-Gerüst steht, ohne dass du es jedes Mal neu tippen musst.

*Einmalig nötig: Unter Einstellungen → **Templates** einen Ordner für deine Vorlagen festlegen, z. B. `templates/`.*

**Mini-Übung:** Lege ein Template namens „Neues Konzept" an, das die Felder `type`, `status` und `sources` leer vorgibt und `created` automatisch auf `{{date}}` setzt. Erzeuge daraus eine neue Notiz.

*Ausblick: Wenn du Templates ausreizt, ist das Community-Plugin **Templater** der nächste Schritt — es kann beim Anlegen nach Werten fragen („Wie heißt die Kundin?"), den Dateinamen setzen, die Notiz automatisch in den richtigen Ordner verschieben und kleine Skripte ausführen. Für alles in diesem Kapitel brauchst du es nicht.*

## Feature 4 (Ausblick, ohne Übung): Cron

Es gibt eine Externe Erweiterung namens **„Cron"** (`obsidian-cron`), das Obsidian-Befehle oder eigene Skripte nach echter Cron-Syntax zeitgesteuert ausführt — solange Obsidian offen bzw. im Hintergrund läuft.

**Business-Beispiel:** Ein wöchentlicher Job, der veraltete Notizen findet (mehr dazu, wie man „veraltet" sauber definiert, in Kapitel 6) und automatisch auf `status: draft` zurücksetzt oder eine Erinnerungs-Notiz erzeugt — „diese [[SOP]]s müssen überprüft werden."

---

*Einige Ideen in diesem Kapitel (Templates pro Notiz-Typ, Bases statt Dataview für Datenbank-Ansichten) sind inspiriert durch: Bruno Paz, „How I use Obsidian to take notes and manage all my knowledge", brunopaz.dev, 5. Februar 2026. [brunopaz.dev/blog/how-i-use-obsidian-to-take-notes-and-manage-all-my-knowledge](https://brunopaz.dev/blog/how-i-use-obsidian-to-take-notes-and-manage-all-my-knowledge/)*
