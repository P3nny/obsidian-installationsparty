---
type: Konzept
---

Ein Ordner, den [[Git]] überwacht — samt seiner kompletten Vorgeschichte. Kurz: „Repo".

Technisch entsteht ein Repository durch den Befehl `git init`. Danach liegt im Ordner ein unsichtbarer Unterordner `.git`, in dem sämtliche [[Commit]]s gespeichert sind. Der Ordner selbst sieht aus wie vorher; die Zeitmaschine steckt unsichtbar daneben.

Ein Repository kann an zwei Orten liegen: **lokal** auf deinem Rechner und **remote** bei einem Dienst wie [[GitHub]]. Beide enthalten denselben Verlauf, und du gleichst sie mit `push` (hoch) und `pull` (runter) ab.

Für diesen Workshop wird dein [[Vault]] zum Repository — ein ganz normaler Notizordner, der sich zusätzlich merkt, wie er letzte Woche aussah.
