# 1. Installation GIT Bash

Um mit GIT auf einem Windwos Client zu arbeiten müssen wir folgende Software installieren. Mit dieser Software wird in den nächsten Schritten gearbeitet.

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

---

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

## Dateien aus dem Repository wiederherstellen

Hier muss man die Commit ID angeben zu der man zurückgreifen will.

Hier ein Beispiel: 

    $ git checkout 323EFG

![Bild](/img/SNAG-0026.png)

![Bild](/img/SNAG-0027.png)

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

---

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

---

# 5. MERGIN

Mit git merge werden mehrere Commit-Abfolgen in einen einheitlichen Verlauf zusammengeführt. Vor allem wird git merge genutzt, um zwei Branches zu vereinen.

    $ git checkout master
    $ git merge dev

![Bild](/img/SNAG-0008.png)

## Merge Konflikt

Konflikte entstehen in der Regel dann, wenn zwei Personen dieselben Zeilen in einer Datei geändert haben oder ein Entwickler eine Datei löscht, während ein anderer Entwickler diese ändert. In diesen Fällen kann Git nicht automatisch entscheiden, welcher Vorgang richtig ist.

---

# 6. Lokales GIT nun mit GitHub verknüpfen

Nun in den obigen Beispielen haben wir Lokal auf unserer Maschine mit GIT BASH gearbeitet.
Wir werden dieses Repo nun mit GitHub verknüpfen.

Dafür installieren wir uns die Desktop-APP von GitHub. Die Desktop APP vereinfacht das Arbeiten mit Repos. Durch die Desktop APP verfallen die ganze Befehle etc. Dies wird einfach durch das GUI vereinfacht und der User muss die Befehle für Git nicht selbst eingeben. Man kann die Commits, Push Pull etc. ganz einfach über die Web Konsole machen.

[Download GitHub](https://desktop.github.com/)

Wenn dies installiert ist starten wird das Programm und fügen das vorherig erstelle Reop zu GitHub hinzu. Dafür geht man wie folgt vor:

![Bild](/img/SNAG-0009.png)

![Bild](/img/SNAG-0010.png)

![Bild](/img/SNAG-0011.png)

![Bild](/img/SNAG-0012.png)

Wenn dies erfolgreich durchlief, sieht man nun sein erstelles Repo auf GitHub.

Dies sieht in meinem Falls so aus:

[GitHub Repo von Leandro](https://github.com/ask-yo-girl-about-me/DBO_Zusatzaufgabe.git)

## Dateien erstellen GitHub

Man kan auch direkt auf der GitHub seite arbeiten. Hier wird gezeigt, wie man ein File erstellt.

![Bild](/img/SNAG-0013.png)

## Neuer Branche erstellen GitHub

Oben haben wir gesehen, wie man ein neuen Branche per Git Bash erstellt. Hier sieht man wie dies übe die GitHub Seite funktioniert.

![Bild](/img/SNAG-0014.png)

![Bild](/img/SNAG-0015.png)

![Bild](/img/SNAG-0016.png)

![Bild](/img/SNAG-0017.png)


# Konflikt Behandlung

Hier schauen wir noch die Konfliktbehandlung han. Dies wird mit dem Beispiel GitHub Webseite und GitHub Desktop APP nachgestellt.

Ich werde auf der GitHub Seite eine Textdatei anpassen. Die gleiche Textdatei werde ich Lokal auf meinem PC ebenfalls anpassen und dann werden wir schauen was passiert.

Hier wird das Textfile auf der GitHub Seite angepasst und direkt gespeichert.

![Bild](/img/SNAG-0018.png)

Hier wird nun ohne das man die änderungen schon sieht das File ebenfalls lokal auf dem Client angepasst

![Bild](/img/SNAG-0019.png)

Nun wollen wir die änderungen auf dem Client commiten.

![Bild](/img/SNAG-0020.png)

Nun kommt die Meldung, dass dieses File in der Zwischenzeit schon angepasst wurde.

![Bild](/img/SNAG-0021.png)

Jetzt müssen wir die Konflikte beheben damit wir wieder weiterarbeiten können.

![Bild](/img/SNAG-0022.png)

Ich habe nun das Textfile im Explorer geöffnet und sehe jetzt beide änderungen. Da es keine grosse verschiedenheit gibt, Akzeptiere ich den Merge.

![Bild](/img/SNAG-0023.png)

Nun funktioniert die ganze Synchronisation wieder erfoglreich.

![Bild](/img/SNAG-0024.png)

# VisualStudioCode als Allrounder

Es gibt verschieden Software um mit Git zu arbeiten.

VisualStudioCode ist ein Programm, die deine Arbeit mit Git direkt vereinfacht und zusammenführt.

Man kann direkt seine Files etc. anpassen und ohne Befehle auswenig lernen direkt aus dem Programm Push Pull und alle anderen Befehle ebenfalls machen.

![Bild](/img/SNAG-0025.png)