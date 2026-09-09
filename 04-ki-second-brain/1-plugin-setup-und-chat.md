# KI-Second-Brain

Dieses Kapitel hat fünf Teile:

| Teil | Worum es geht |
|---|---|
| 1 (hier) | Claudian einrichten, erster Chat mit dem Vault |
| 2 | Wissen reinholen — Web Clipper und Rohnotizen |
| 3 | Verdichten und Wiederfinden — der eigentliche Kreislauf |
| 4 | Dasselbe mit deinem eigenen Wissen |
| 5 | OKF — Vertiefung, optional |

Dieser erste Teil legt die Basis für alles Weitere.

## Was ist Claudian?

Claudian ist das Obsidian-Plugin, das Claude direkt in deinen Vault holt. Im Hintergrund nutzt es die **Claude Code CLI** — dieselbe Technik, mit der Entwicklerinnen Claude im Terminal steuern, nur eben eingebettet in Obsidian statt in einem separaten Fenster.

*Häufige Frage an dieser Stelle: Werden meine Notizen fürs KI-Training verwendet, und warum weiß Obsidian nichts von früheren Chats? Beides beantwortet [[Claude Code Datenfluss]].*

**Voraussetzung für dieses Kapitel:** Du solltest dein Terminal kennen und Claude Code CLI und Claudian müssen installiert sein. Falls Du das noch nicht hast, bitte erst zu [[00-installation#Teil B: Vor Kapitel 4 (KI-Second-Brain)|Installation, Teil B]]. 

---

## Warum überhaupt Markdown-Dateien fürs Second Brain?

Bevor es an die Übungen geht, kurz die Begründung, warum das ganze Setup — Markdown, Obsidian und eine KI mit Vault-Zugriff — überhaupt sinnvoll ist.

**Der Kern:** Eine `.md`-Datei ist einfach **Text**. Ein `.pdf` oder `.docx` ist dagegen ein **Layout-Format** — es beschreibt vor allem, wo auf einer Seite etwas steht, nicht in erster Linie, was inhaltlich zusammengehört.

| | Markdown (.md) | PDF | Word (.docx) |
|---|---|---|---|
| Was die KI tatsächlich sieht | reiner Text, direkt lesbar | muss erst „extrahiert" werden — Spalten, Tabellen, Kopf-/Fußzeilen verwischen oft | XML mit viel Formatierungs-Ballast drumherum |
| Struktur erkennbar | ja, `#`-Überschriften markieren klar Abschnitte | oft verloren (Layout ≠ Struktur) | teilweise, aber mit Rauschen vermischt |
| Diffbar/versionierbar (Git) | ja, Zeile für Zeile | nein, binär | nein, binär |
| Werkzeug-unabhängig | jeder Texteditor öffnet es, auch in 20 Jahren noch | proprietäres Rendering nötig | an Microsoft-Ökosystem gebunden |
| Metadaten maschinenlesbar | ja — als [[Frontmatter]], siehe Kapitel 3 | nein, nur separat denkbar | nur versteckt in Word-eigenen Feldern |
| Durchsuchbar mit Bordmitteln | ja — auch ganz ohne KI, mit einem einzigen Terminal-Befehl (siehe Bonus-Kapitel Command Line) | nein, erst Text-Extraktion nötig | nein, erst Konvertierung nötig |

**Weitere Aspekte, die für dieses Setup sprechen:**

- **Token-Effizienz:** Reiner Text braucht keine Formatierungs-„Verpackung" — bei PDF/Word geht ein Teil des Kontextfensters für Layout-Ballast drauf, der inhaltlich nichts beiträgt.
- **Natürliche Chunk-Grenzen:** Ein Plugin muss Notizen in Häppchen zerlegen, um sie zu durchsuchen. Markdown-Überschriften liefern dafür saubere Bruchstellen — bei einem PDF ohne erkennbare Struktur muss das Tool raten, wo ein Gedanke endet.
- **Ein lebendiges System:** Anders als ein einmal geschriebenes Dokument wächst der Vault mit jeder neuen Notiz — die KI „kennt" das Neue sofort, ohne neu trainiert zu werden.
- **Versionsgeschichte des eigenen Denkens** *(Bogen zu Bonus-Git)*: Weil es Text ist, lässt sich ggf. mit [[Git]] nachvollziehen, wie sich eine Idee über Wochen verändert hat.

---

## Second Brain erfahrbar machen: drei Übungen

### Übung 1: Multi-Hop-Frage

Nicht „Was ist ein Zettelkasten?" (steht wortwörtlich in einer Datei) — das wäre reines Nachschlagen. Frag stattdessen etwas, das zwei Notizen verknüpft:

> „Wann könnte ich mit Frau Sarnowski einen Termin für den Kickoff von Phase 2 machen?"

Das Plugin muss dafür `Kundenprojekt-Lotos.md` (wer ist das, welche Phase steht an) und `Arbeitspräferenzen.md` (keine Termine vor 10 Uhr, freitags keine Workshops) gleichzeitig heranziehen. Keine der beiden Notizen erwähnt die andere — die Brücke muss die KI selbst bauen. Das ist der eigentliche Second-Brain-Moment: Eine Verbindung taucht auf, die du nirgends hingeschrieben hast.

**Worauf du achten kannst:** Nennt die Antwort einen konkreten Zeitrahmen *und* begründet ihn mit deinen Regeln — statt nur „Frau Sarnowski ist die Ansprechpartnerin für Lotos" zu wiederholen?

### Übung 2: Live-Wachstum

Lege eine neue Notiz `Mein-Eindruck-Workshop.md` an, mit 1–2 Sätzen zu deinem bisherigen Eindruck vom Workshop. Stell danach sofort eine Frage, die nur mit dieser brandneuen Notiz beantwortbar ist, z. B.:

> „Was habe ich zu meinem Eindruck vom Workshop notiert?"

**Worauf du achten kannst:** Das Plugin muss die Notiz nicht „gelernt" haben — sie war Sekunden vorher noch nicht da, und trotzdem taucht sie in der Antwort auf. Das „Gedächtnis" wächst live mit, ganz ohne Neu-Training.

### Übung 3: Kontrast — mit vs. ohne Vault-Zugriff

Stell dieselbe Frage zweimal:

1. Im normalen claude.ai-Browser-Tab **ohne** Vault-Anbindung
2. Im Obsidian-Plugin **mit** Vault-Zugriff

Die Frage dafür:

> „Was weißt du über das Kundenprojekt Lotos?"

**Worauf du achten kannst:** Ohne Vault-Zugriff kann die KI diese Frage unmöglich sinnvoll beantworten — „Lotos" ist eine frei erfundene, private Notiz, die außerhalb deines Vaults nirgendwo existiert. Mit Vault-Zugriff liefert das Plugin dagegen konkrete Details (Ansprechpartnerin, Projektstatus). Der Unterschied zwischen einer generischen Ausrede und einer fundierten Antwort macht den Wert des Setups greifbar spürbar statt nur behauptet.

*Zusatz, falls Zeit bleibt:* Stell eine Frage, die garantiert nicht im Vault steht (z. B. „Was ist die Hauptstadt von Frankreich?"). Zeigt: Das Plugin blendet nicht einfach alles andere aus, sondern ergänzt Vault-Wissen um allgemeines Wissen — wichtig fürs richtige mentale Modell, was das Tool eigentlich tut.

---

## Ein letzter Blick: Was heißt hier eigentlich „agentisch"?

Bisher hast du gefragt, Claudian hat im Vault gesucht und geantwortet — reiner Text. Jetzt eine Stufe weiter: Bitte Claudian, tatsächlich etwas zu **tun**, nicht nur zu beschreiben:

> „Leg eine neue Notiz `Terminal-Test.md` an, mit `type: Test` im Frontmatter und einem Satz Inhalt."

Schau in der Dateiliste nach — die Notiz ist wirklich da, ganz ohne dass du selbst geklickt oder getippt hast. Genau das unterscheidet eine [[Agentische KI|agentische KI]] von einem gewöhnlichen Chatbot:

| | Chatbot | Agentische KI |
|---|---|---|
| Ergebnis | Text, den du selbst umsetzen musst | echte Aktion — Datei wurde erstellt/verändert |
| Ablauf | eine Antwort, fertig | plant, handelt, prüft das Ergebnis, bessert nach |
| Beispiel hier | „So könnte deine Notiz aussehen: ..." | Notiz existiert tatsächlich im Vault |

Dafür nutzt Claudian im Hintergrund dieselbe Kommandozeile, die du in der Installation ([[00-installation#Schritt 5: Claude Code CLI installieren|Schritt 5]]) mit `claude --version` kurz angetestet hast — nur eben automatisiert statt von dir selbst getippt.

**Neugierig, was da im Hintergrund wirklich passiert?** Genau darum geht's im **Bonus-Kapitel [[1-command-line]]**.

**Weiter geht's in Teil 2 [[2-wissen-reinholen]]:** Wie Wissen überhaupt in den Vault kommt — per Web Clipper aus dem Browser und als hingekritzelte Rohnotiz.
