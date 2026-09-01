# KI-Erweiterung

Dieses Kapitel hat vier Teile: Plugin-Setup & Chat (hier), Workflow – Notiz zu OKF, Second-Brain-Übung und Vergleich verschiedener KI-Setups. Dieser erste Teil legt die Basis für die anderen drei.

## Bevor es losgeht: Plugin verbinden

*Falls du das schon in der Vorbereitung (Teil C, Schritt 6b) erledigt hast, kannst du diesen Abschnitt überspringen — je nachdem, wie eure Gruppe durch den Workshop kommt, haben manche das schon hinter sich, andere holen es jetzt nach.*

In der Vorbereitung (Teil C) hast du bereits **Ollama** mit dem Modell `llama3.2` installiert. Jetzt verbindest du das mit Obsidian:

1. Einstellungen → **Externe Erweiterungen** → **Durchsuchen**
2. Installiere **„Copilot"** (oder alternativ „Text Generator") und aktiviere es

⚠️ **Namensfalle:** Dieses Obsidian-Plugin heißt zufällig auch „Copilot" — hat aber nichts mit GitHub Copilot oder Microsoft 365 Copilot zu tun. Reiner Zufall bei der Namensgebung.

3. In den Plugin-Einstellungen: Provider auf **Ollama** stellen, Modell `llama3.2` auswählen — läuft lokal auf `localhost`, keine weiteren Zugangsdaten nötig
4. *Falls du in der Vorbereitung Schritt 7 einen Claude-API-Key eingerichtet hast:* Trag ihn schon mal als zweiten Provider ein, du wechselst später in der Übung „Kontrast" dazwischen hin und her

---

## Warum überhaupt Markdown-Dateien fürs Second Brain?

Bevor es an die Übungen geht, kurz die Begründung, warum das ganze Setup — Markdown, Obsidian, OKF — überhaupt sinnvoll ist, wenn man mit KI arbeiten will.

**Der Kern:** Eine `.md`-Datei ist einfach **Text**. Ein `.pdf` oder `.docx` ist dagegen ein **Layout-Format** — es beschreibt vor allem, wo auf einer Seite etwas steht, nicht in erster Linie, was inhaltlich zusammengehört.

| | Markdown (.md) | PDF | Word (.docx) |
|---|---|---|---|
| Was die KI tatsächlich sieht | reiner Text, direkt lesbar | muss erst „extrahiert" werden — Spalten, Tabellen, Kopf-/Fußzeilen verwischen oft | XML mit viel Formatierungs-Ballast drumherum |
| Struktur erkennbar | ja, `#`-Überschriften markieren klar Abschnitte | oft verloren (Layout ≠ Struktur) | teilweise, aber mit Rauschen vermischt |
| Diffbar/versionierbar (Git) | ja, Zeile für Zeile | nein, binär | nein, binär |
| Werkzeug-unabhängig | jeder Texteditor öffnet es, auch in 20 Jahren noch | proprietäres Rendering nötig | an Microsoft-Ökosystem gebunden |
| Metadaten maschinenlesbar | ja — genau das ist das OKF-Frontmatter aus Kapitel 3 | nein, nur separat denkbar | nur versteckt in Word-eigenen Feldern |
| Durchsuchbar mit Bordmitteln | ja — `grep` aus Kapitel 5 funktioniert direkt | nein, erst Text-Extraktion nötig | nein, erst Konvertierung nötig |

**Weitere Aspekte, die für dieses Setup sprechen:**

- **Token-Effizienz:** Reiner Text braucht keine Formatierungs-„Verpackung" — bei PDF/Word geht ein Teil des begrenzten Kontextfensters für Layout-Ballast drauf, der inhaltlich nichts beiträgt. Bei einem lokalen Modell wie unserem Llama 3.2 zählt das besonders.
- **Natürliche Chunk-Grenzen:** Ein Plugin muss Notizen in Häppchen zerlegen, um sie zu durchsuchen. Markdown-Überschriften liefern dafür saubere Bruchstellen — bei einem PDF ohne erkennbare Struktur muss das Tool raten, wo ein Gedanke endet.
- **Herkunft nachvollziehbar:** Weil unsere Notizen `sources`/`status` im OKF-Frontmatter tragen, kann ein gutes Plugin beim Antworten angeben, aus welcher Notiz eine Aussage stammt.
- **Ein lebendiges System:** Anders als ein einmal geschriebenes Dokument wächst der Vault mit jeder neuen Notiz — die KI „kennt" das Neue sofort, ohne neu trainiert zu werden.
- **Versionsgeschichte des eigenen Denkens** *(Bogen zu Bonus-Git)*: Weil es Text ist, lässt sich mit Git nachvollziehen, wie sich eine Idee über Wochen verändert hat.

---

## Second Brain erfahrbar machen: drei Übungen

### Übung 1: Multi-Hop-Frage

Nicht „Was ist OKF?" (steht wortwörtlich in einer Datei) — das wäre reines Nachschlagen. Frag stattdessen etwas, das zwei Notizen verknüpft:

> „Wie hängen Zettelkasten und OKF zusammen?"

Das Plugin muss dafür `Zettelkasten.md` und `OKF.md` gleichzeitig heranziehen und selbst eine Brücke bauen, die so in keiner der beiden Dateien steht. Das ist der eigentliche Second-Brain-Moment: Eine Verbindung taucht auf, die du nicht explizit hingeschrieben hast.

**Worauf du achten kannst:** Erwähnt die Antwort beide Konzepte aus eigenem Kontext (Luhmanns permanente Notizen *und* OKFs maschinenlesbare Vertrauens-Metadaten) und stellt selbst eine Verbindung her — z. B. dass OKF im Grunde formalisiert, was Zettelkasten informell schon anstrebt: Notizen, die auch nach Jahren noch verlässlich nutzbar sind?

### Übung 2: Live-Wachstum

Lege eine neue Notiz `Mein-Eindruck-Workshop.md` an, mit 1–2 Sätzen zu deinem bisherigen Eindruck vom Workshop. Stell danach sofort eine Frage, die nur mit dieser brandneuen Notiz beantwortbar ist, z. B.:

> „Was habe ich zu meinem Eindruck vom Workshop notiert?"

**Worauf du achten kannst:** Das Plugin muss die Notiz nicht „gelernt" haben — sie war Sekunden vorher noch nicht da, und trotzdem taucht sie in der Antwort auf. Das „Gedächtnis" wächst live mit, ganz ohne Neu-Training.

### Übung 3: Kontrast — mit vs. ohne Vault-Zugriff

Stell dieselbe Frage zweimal:

1. Im normalen Ollama- oder Claude-Chat **ohne** Vault-Anbindung (z. B. direkt im Terminal mit `ollama run llama3.2`, oder im claude.ai-Browser-Tab)
2. Im Obsidian-Plugin **mit** Vault-Zugriff

Die Frage dafür:

> „Was weißt du über das Kundenprojekt Lotos?"

**Worauf du achten kannst:** Ohne Vault-Zugriff kann die KI diese Frage unmöglich sinnvoll beantworten — „Lotos" ist eine frei erfundene, private Notiz, die außerhalb deines Vaults nirgendwo existiert. Mit Vault-Zugriff liefert das Plugin dagegen konkrete Details (Ansprechpartnerin, Projektstatus). Der Unterschied zwischen einer generischen Ausrede und einer fundierten Antwort macht den Wert des Setups greifbar spürbar statt nur behauptet.

*Zusatz, falls Zeit bleibt:* Stell eine Frage, die garantiert nicht im Vault steht (z. B. „Was ist die Hauptstadt von Frankreich?"). Zeigt: Das Plugin blendet nicht einfach alles andere aus, sondern ergänzt Vault-Wissen um allgemeines Wissen — wichtig fürs richtige mentale Modell, was das Tool eigentlich tut.

---

**Bogen zurück zu Kapitel 5:** `grep -r "OKF" . --include="*.md" | sort` aus der Command-Line-Übung war im Grunde schon eine ganz einfache, manuelle Form von „Wissen wiederfinden" — nur ohne KI-Zusammenfassung danach und ohne die Fähigkeit, mehrere Fundstellen selbstständig zu verknüpfen. Das Plugin automatisiert genau das.

**Weiter geht's in Teil 2:** Workflow — wie aus einer unstrukturierten Notiz automatisch eine OKF-konforme wird.
