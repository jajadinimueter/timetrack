Timetrack
=========

Zeiterfassungssoftware als Übung für Methoden der Programmierung

Source Control
--------------

Zur Source-Verwaltung wird git verwendet. Das Repository lassen wir von github hosten.
Dies aus folgenden Gründen:

 * Das Projekt ist eine Übung und darf darum durchaus öffentlich zugängig sein.
 * Es muss kein eigener Server aufgesetzt werden, was Zeit und Kosten spart.

Als Branching-Modell wird das von Vincent Driessen vorgeschlagene verwendet ([Git-Branching-Model](http://nvie.com/posts/a-successful-git-branching-model/)).
Das heisst, die Mitglieder der Gruppe entwickeln im develop branch. Sobald
ein Release ready ist, wird der develop branch in den master gemerged und getagged.
Nur hotfixes dürfen danach noch direkt in den master gepushed werden.


CI
--

Für die CI wird [travis](https://travis-ci.org/) verwendet.

Hier der [Direktlink zu den Builds](https://travis-ci.org/jajadinimueter/timetrack).

Dieser Service ist gratis und lässt sich wunderbar zusammen mit github benutzen. Github hat sogar
eine travis-Integration.


Projekt aufsetzen und kompilieren
---------------------------------

Dafür wird Apache maven und Idea Intellij verwendet. Durch das Benutzen von maven für den
Build-Prozess und das Fetchen von Abhängigkeiten kann sichergestellt werden, dass das
Projekt bei jedem Mitglied der Gruppe gebuildet werden kann.

Mit dem Goal `mvn jetty:run` kann lokal der Jetty gestartet werden.

Tests
-----

Tests werden via `mvn test` target laufen gelassen. Maven verwendet dann alle Unittests unter
`main/test/java`.


Deployment
----------

Mit dem maven wagon plugin.

`mvn wagon:upload-single` ausführen.

Das Projekt wird mit scp deployed. Leider haben wir bis jetzt noch keinen Server,
darum haben wir diesen Task erst vorbereitet. Sobald wir einen Server haben,
können wir die Properties `deploy.url` und `deploy.path` anpassen und das `war`-File
auf den Server deployen.




