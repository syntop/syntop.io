syntop.io Website
=================


Lokales Setup auf OSX
---------------------

1.  [Bonsai](http://tinytree.info/) installieren:  
    `sudo gem install bonsai`
2.  Repository klonen:  
    `git clone git@github.com:syntop/syntop.io.git`
3.  Ins Verzeichnis wechseln:  
    `cd syntop.io`
4.  Das GitHub-Pages-Repository ins Unterverzeichnis `site` klonen:  
    `git clone -b gh-pages git@github.com:syntop/syntop.io.git`
5.  Lokalen Webserver starten:  
    `bonsai --cultivate`
6.  Hacken.


Projektstruktur
---------------

### Content

Die Inhalte der Website befinden sich im Verzeichnis `content`. Jeder 
Unterordner entspricht einer Seite der Website. Die Namen der Unterordner
enthalten ein numerisches Präfix, das der Sortierung dient, z.B.
`20120321.foobar`. Dadurch, dass wir Datumsangaben als Präfix benutzen, werden
die Projekte auf der Website chronologisch aufgelistet. Der Ordner `index`
entspricht der Startseite.

In jedem Unterordner befindet sich eine Datei mit der Endung `.yml`. Diese
enthält den Content der jeweiligen Seite. Der Teil des Dateinamens vor dem
`.` definiert das Template, das für diese Seite verwendet werden soll. 
Beispiel: `20120321.foobar/project.yml` verwendet das Template `project.liquid`.
Bilder zu einem Projekt werden im Unterordner `images` des Projektordners
abgelegt.

### Statische Dateien (CSS, JS, etc.)

Die statischen Assets liegen im Ordner `public` und werden automatisch »as-is«
ins Root-Verzeichnis der Website kopiert.

### Templates

Die **Templates** liegen im Ordner `templates`. Wir benutzen [Liquid](http://liquidmarkup.org/)
als Template-Sprache. 


Generieren der statischen Website
---------------------------------

Ein Aufruf von `bonsai --repot` generiert eine statische Version der Website im
Ordner `output`. 


Update von syntop.io
--------------------

Um die Website unter [dev.syntop.io](http://dev.syntop.io/) zu aktualisieren,
reicht ein Aufruf von `rake deploy` im Projekthauptverzeichnis.