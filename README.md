# 1. Installation GIT Bash

[Download Git Bash](https://git-scm.com/downloads)

---

# 2. Einrichtung Repository

Hier wird aufgezeigt, wie man ein Repository erstellt und initialisieren dies als git verzeichnis.

Wir öffnen nun das neu installierte Programm "GIT CMD".

Wir wechseln nun in das gewünschte Verzeichnis:

    cd "Pfad"

Nun erstellen wir ein neues Verzeichnis:

    mkdir DBO_Zusatzaufgabe

 Erstellen eines leeren Git-Repositorys oder Reinitialisierung eines vorhandenen Repositorys

    git init

![Bild](/img/SNAG-0000.png)

# 3. Im Repository arbeiten

Erstellen eines Textfiles

    copy con file1branche1.txt

![Bild](/img/SNAG-0001.png)

## Datei zur Versionskontrolle hinzufügen

    git add file1branche1.txt
    git status

## Die Dateien Commiten
    $ git commit -m "file1branche1.txt erstellt"
    $ git status

Hier sehen wir nun die Ausgaben der oben aufgelisteten Befehlen

![Bild](/img/SNAG-0002.png)

## Datei aus der Versionskontrolle wieder löschen
    $ git add file2branche1.txt
    $ git rm --cached file2branche1.txt
    $ git status

![Bild](/img/SNAG-0004.png)

## Die Commit History

Zeigt die Commit-Protokolle an.

Listet die Commits auf, die über die übergeordneten Links von den angegebenen Commits aus erreichbar sind, schließt aber Commits aus, die von den angegebenen Commits aus erreichbar sind, denen ein ^ vorangestellt ist. Die Ausgabe erfolgt standardmäßig in umgekehrter chronologischer Reihenfolge.

    $ git log

![Bild](/img/SNAG-0003.png)

## Lokale Änderungen rückgängig machen

Hier ändern wir das file1branche1.txt Lokal auf unserem Computer. Danach machen wir über das GIT CMD diese änderung rückgängig. Nach dem wir diesen Befehl eingegeben haben darf unsere Änderung nicht mehr sichbar sein.

    $ git checkout HEAD -- file1branche1.txt
    $ git status

![Bild](/img/SNAG-0005.png)

## Änderungen in der Stage Area rückgängig machen

Hier können wir änderungen welche schon gestaged wurden wieder rückgängig machen. Dies erfolgt über zwei Varianten. Eine einzelne Datei oder alles auf einmal zu reseten.

## Um eine einzelne Datei rückgängig zu machen
    $ git status
    $ git reset -- file1branche1.txt
    $ git status

## Um alles zu entfernen
    $ git reset

# 4. Branching

In Git sind Branches Bestandteil deines alltäglichen Entwicklungsprozesses. Git-Branches sind quasi Verweise auf einen Snapshot deiner Änderungen. Wenn du ein neues Feature hinzufügen oder einen Fehler beheben möchtest, legst du einen neuen Branch an, der deine (großen oder kleinen) Änderungen enthält.

## Neuer Branch erstellen
    $ git branch dev

Mit dem checkout Befehl können wir zu einem anderen Branch wechseln.

    $ git checkout dev
    $ git status

>TIP: Die Brancherstellung (branch dev) und den Wechsel in den neuen Branch (checkout dev) kann man auch in einem Befehl durchführen:

    $ git checkout -b dev

Wir erstellen eine neue Datei "file1branche2.txt" und commiten
diese ins den Dev Branch, also den neu erstellen Branche.

    $ copy con file1branche2.txt
    $ git add file1branche2.txt
    $ git commit -m "neue Datei file4branche2.txt in Branche 2"
    $ git status

![Bild](/img/SNAG-0006.png)

## Zurück in den Master wechseln

Nun wechseln wir wieder zurück auf den "master" Branch.
Befehl:

    $ git checkout master

![Bild](/img/SNAG-0007.png)

# 5. MERGIN

Mit git merge werden mehrere Commit-Abfolgen in einen einheitlichen Verlauf zusammengeführt. Vor allem wird git merge genutzt, um zwei Branches zu vereinen.

    $ git checkout master
    $ git merge dev

![Bild](/img/SNAG-0008.png)

## Merge Konflikt

Konflikte entstehen in der Regel dann, wenn zwei Personen dieselben Zeilen in einer Datei geändert haben oder ein Entwickler eine Datei löscht, während ein anderer Entwickler diese ändert. In diesen Fällen kann Git nicht automatisch entscheiden, welcher Vorgang richtig ist.

# 6. Lokales GIT nun mit GIT-HUB verknüpfen


