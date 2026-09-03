# OKF – Open Knowledge Format

*In den ersten vier Teilen hast du mehrfach `type` und `status` ins [[Frontmatter]] geschrieben — mal selbst, meistens von der KI. Dafür gibt es eine ausformulierte Konvention, und die heißt OKF. Dieser Teil ist die Vertiefung für alle, die es jetzt genauer wissen wollen. Kein Muss, um mit dem Workshop fertig zu sein — aber ein Blick unter die Haube.*

Basiert auf der offiziellen Spezifikation von Google: [github.com/GoogleCloudPlatform/knowledge-catalog](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md). Für diesen Workshop reicht ein vereinfachter Ausschnitt der Kernfelder.

## Was ist OKF

OKF ist ursprünglich für Datenmanagement in Unternehmen gedacht: eine Konvention aus Markdown-Datei + YAML-Frontmatter, die sagt, woher eine Notiz stammt, wie sehr man ihr vertrauen kann und ob sie noch aktuell ist.

Der Ausgangspunkt ist genau das Problem, das du in Teil 3 im Kleinen gelöst hast — nur eben mit zehntausend Dateien statt zehn. In Unternehmen liegt Wissen verteilt über Wikis, Handbücher, Datenbank-Beschreibungen und verstreute Markdown-Dateien. Fragt man eine KI etwas, das mehrere dieser Quellen berührt, kommen oft unvollständige Antworten heraus. Der entscheidende Punkt daran: **Das liegt selten am Modell, sondern daran, wie das Wissen abgelegt ist.**[^1]

Deshalb hat Google für OKF bewusst kein neues Werkzeug gebaut, sondern nur eine Konvention für etwas, das es überall schon gibt — Markdown. Wer schreibt, schreibt weiter wie bisher; die KI bekommt über das Frontmatter zusätzlich mitgeteilt, was ein Dokument eigentlich ist und wie es mit anderen zusammenhängt.

*Der Clip `Clippings/What is Google OKF (Open Knowledge Format).md` geht auf diese Unternehmens-Perspektive ausführlicher ein — praktisches Übungsmaterial: Lass ihn dir von Claudian zusammenfassen und mit dieser Notiz vergleichen.*

## Zwei Vokabeln vorweg

OKF nennt eine einzelne Datei ein **Concept** und die ganze Sammlung ein **Bundle**. Das klingt akademisch, ist aber praktisch: Ein Concept ist genau eine Notiz — Frontmatter oben, Markdown darunter. Ein Bundle ist ein Ordnerbaum voller solcher Dateien, der für sich allein funktioniert.

**Dein Vault ist ein Bundle.** Mehr Übersetzung braucht es nicht.

## Die Felder

**Pflicht ist genau eins:**

| Feld | Bedeutung |
|---|---|
| `type` | Was für ein Ding ist das? Frei wählbar, keine Vorgabeliste — `SOP`, `Kundenprojekt`, `Metric`, `Playbook` |

Dass ausgerechnet `type` die einzige Pflichtangabe ist, hat einen praktischen Grund (siehe Teil 3): Es ist das Feld, über das eine KI gezielt *alle Notizen einer Art* findet, statt im Fließtext auf passende Stichwörter angewiesen zu sein.

**Empfohlen, weil die KI damit viel anfangen kann:**

| Feld | Bedeutung |
|---|---|
| `title` | lesbarer Anzeigename |
| `description` | **ein** Satz, der das Ding zusammenfasst |
| `resource` | Link auf das, was beschrieben wird (Datei, Tool, Kundenordner) |
| `tags` | Liste für querliegende Kategorien |

**Herkunft und Vertrauen — hier wird OKF interessant:**

| Feld | Bedeutung |
|---|---|
| `sources` | Liste von Quellen. Pro Eintrag ist `resource` Pflicht, dazu optional `title`, `author`, `last_modified` |
| `generated` | Wer hat es *erstellt*: `{ by: ..., at: ... }`. Akteure werden notiert als `human:patricia`, `process:import-skript` oder `werkzeug/version` |
| `verified` | Wer hat es *geprüft*: dieselbe Form, aber als Liste — mehrere Prüfungen sind erlaubt |
| `status` | `draft`, `stable` oder `deprecated`. **Fehlt das Feld, gilt `stable`** |
| `stale_after` | fester Zeitpunkt, ab dem der Inhalt als veraltet gilt |

### Der wichtigste Denkfehler

`generated` und `verified` sehen ähnlich aus, meinen aber Verschiedenes: **erstellt** ist nicht **geprüft**. Ein KI-Entwurf, den nie jemand gegengelesen hat, hat ein `generated`, aber kein `verified`.

Und die eigentliche Pointe: Es gibt kein Feld „Vertrauenswürdigkeit". Die Vertrauensstufe wird aus `verified` **abgeleitet**:

| Stufe | Wann |
|---|---|
| unverified | kein `verified` vorhanden |
| machine-confirmed | `verified` nur von Maschinen |
| human-reviewed | mindestens ein `human:...` hat geprüft |

Niemand kann also behaupten, etwas sei vertrauenswürdig — man kann nur festhalten, wer wann draufgeschaut hat. Die Stufe ergibt sich daraus von selbst.

## Ein vollständiges Beispiel

Im Vault liegt eine Notiz, die alle Felder in einem echten Anwendungsfall zeigt: [[SOP-Kundenonboarding]]. Öffne sie in der Quellcode-Ansicht und lies das Frontmatter einmal von oben nach unten — dann ist das Format erledigt.

**Übung:** Frag Claudian: „Wie vertrauenswürdig ist die Notiz `SOP-Kundenonboarding` nach OKF-Maßstab, und woran machst du das fest?"

## Nutzen über Datenmanagement hinaus

Egal ob wissenschaftliches Arbeiten oder eigenes Business — dasselbe Feldset trägt beides:

- `sources` ist im Kern ein Zitations- bzw. Herkunftsnachweis: woher ein Kundenwissen, eine Marktrecherche oder ein Zitat stammt, nachvollziehbar auch Monate später
- `verified` unterscheidet eine ungeprüfte Idee von einer gegengelesenen Aussage — bei Forschung ebenso wichtig wie bei einem Angebot, das nie ungeprüft rausgeht
- `status: draft/stable` zeigt, was noch Rohmaterial ist und was belastbar zitier- bzw. verwendbar ist
- `stale_after` macht sichtbar, wann sich verändernde Daten oder Abläufe erneut geprüft werden müssen
- In jedem Fall wird die eigene Notizsammlung KI-lesbar und -durchsuchbar, ohne zusätzliches Tool

## Wofür OKF NICHT gedacht ist

Für ein tägliches Journal oder simple Aufgabenverwaltung wäre OKF überdimensioniert — niemand will bei jedem Tageseintrag `sources` oder `verified` pflegen, dafür reichen einfache Tags.

Die Unterscheidung passt zur Trennung von flüchtigen und permanenten Notizen im [[Zettelkasten]]: OKF ist ein Format für die **permanenten** Notizen — die, die es wert sind, dauerhaft im Second Brain zu bleiben. Genau diesen Übergang — vom freien Journal-Eintrag zu `type`, `status`, irgendwann `verified` — hast du in Teil 3 selbst gemacht, nur dass dort die KI ihn ausgeführt hat.

*Übrigens lässt sich das direkt in den Web Clipper einbauen: In den Vorlagen der Erweiterung kannst du feste Eigenschaften hinterlegen, sodass jeder Clip automatisch mit `type` und `status: draft` ankommt.*

[^1]: Mehul Gupta, „What is Google OKF (Open Knowledge Format)?", Medium, 4. Juli 2026. Liegt als Beispiel-Clip in `Clippings/`.
