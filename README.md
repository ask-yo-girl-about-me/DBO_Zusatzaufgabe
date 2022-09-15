# Installation

https://git-scm.com/downloads

# Einrichtung Repository

    cd "Pfad"
    mkdir DBO_Zusatzaufgabe
    git init

![Bild](/img/SNAG-0000.png)

# Im Repository arbeiten

    mkdir Ordner1
    mkdir Ordner2

    file1branche1.txt
    file2branche1.txt

## Datei zur Versionskontrolle hinzufügen

    git add file1branche1.txt
    git add file2branche1.txt
    git status

## Die Dateien Commiten
    $ git commit -m "file1branche1.txt erstellt"
    $ git status

## Datei aus der Versionskontrolle wieder löschen
    $ git add file2branche1.txt
    $ git rm --cached file2branche1.txt
    $ git status

## Die Commit History
    $ git log

## Lokale Änderungen rückgängig machen
    $ git checkout HEAD -- file1branche1.txt
    $ git status

## Änderungen in der Stage Area rückgängig machen

## Um eine einzelne Datei rückgängig zu machen
    $ git status
    $ git reset -- file1branche1.txt
    $ git status

## Um alles zu entfernen
    $ git reset

# Branching

## Neuer Branch erstellen
    $ git branch dev

Mit dem checkout Befehl können wir zu einem anderen Branch wechseln.

    $ git checkout dev
    $ git status

TIP: Die Brancherstellung (branch dev) und den Wechsel in den neuen Branch (checkout dev) kann man
auch in einem Befehl durchführen:

    $ git checkout -b dev

Wir erstellen eine neue Datei "file1branche2.txt" und commiten
diese ins Repository.

    $ git add file1branche2.txt
    $ git commit -m "neue Datei file1branche2.txt in Branche 2"

## Zurück in den Master wechseln

Nun wechseln wir wieder zurück auf den "master" Branch.
Befehl:

    $ git checkout master

