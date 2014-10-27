# Moodle magische Navigation

Das Informatik Moodle der TU Darmstadt bringt nicht die beste Navigation aller Zeiten mit. Für ein einfaches Wechseln des
Kurses sind viel (sic!) zu viele Klicks notwendig. Außerdem wirkt die Kursliste in der linken Spalte schon nach dem ersten
Semester extrem unübersichtlich, weil sich keine Kurse ausblenden lassen.

Moodle magische Navigation löst als Userscript-Plugin dieses Problem durch eine einfache, elegante und vor allem blitzschnelle
Bedienung.

![Moodle Magische Navigation](https://raw.githubusercontent.com/jlauinger/moodle-magic-navigation/master/screenshot.png)

## Installation

#### Schritt 1

Du verwendest:
 * Chrome, Chromium, Firefox oder Opera
 * Das Plugin Tampermonkey, Greasemonkey bzw. ViolentMonkey
 * Das Standard-Moodletemplate der TU Darmstadt

Mit einem alternativen Moodletemplate kann es sein, dass das Plugin funktioniert, es kann aber auch Fehler geben. Versuche
in diesem Fall einmal das Standard-Template.

#### Schritt 2:

* Erstelle ein neues Userscript, das auf der Seite `https://moodle.informatik.tu-darmstadt.de/*` aktiv ist
* Kopiere den Javascript-Code, der sich in der Datei `moodle-magic-navigation.js` befindet. Die Raw-Ansicht von
  GitHub wird dir dabei helfen
* Füge den Code in das neue Userscript ein

#### Schritt 3:

* Bearbeite das Userscript:
  - In Zeile 23, ersetze `xy42juhu` durch deine TU Id. (Nein, ich speichere diese nicht auf meinem Server...)
  - In Zeile 24, ersetze `Max Mario Mustermann` durch den exakten Namen, der in deinem Moodle bis jetzt oben
    rechts direkt vor (Login) angezeigt wird.
  - In Zeile 25, ersetze `Max Mustermann` durch deinen Namen
* Einmal speichern und fertig

## Konfiguration

Ab Zeile 26 werden die Kurse konfiguriert, die du als Navigationsziele verwenden kannst. Typischerweise solltest
du diese zu Beginn jedes neuen Semesters ändern.

Du kannst beliebig viele neue Kurse hinzufügen. Diese sind immer wie folgt aufgebaut:

```
{
	'name': 'Foo',
	'hotkey': 'f'.charCodeAt(0),
	'courseId': '42'
}
```

Dabei trägst du bei hotkey den Buchstaben ein, den du drücken musst um zum Kurs zu gelangen, und bei courseId die
ID des Kurses, die du in der Moodle-URL herausfinden kannst. Es ist einfach die Zahl ganz am Ende bei ?id=42.

## Verwendung

Auf jeder Moodle-Seite wirst du oben rechts statt deinem Namen und einem Logout-Link ein wunderschönes Menü sehen.

Drücke einen der blau hinterlegten Buchstaben, um zum entsprechenden Kurs zu gelangen. Mit `Entf` kannst du das Menü
schließen. Klicke dann einfach wieder auf die grüne Fläche zum Öffnen. Du wirst merken, dass die gesamte Tastatur
vom Plugin gesperrt wird und du nicht mehr in Textfeldern tippen kannst. Daher kannst du mit `Esc` die Funktionalität
entfernen. Anschließend kannst du wieder tippen. Nach einem Aktualisieren der Seite steht dir die Navigation wieder
zur Verfügung.

Viel Spaß!

## Lizenz

Der Code steht unter der GNU GPL in Version 2. Hilf mir gerne bei der Weiterentwicklung und erstelle einen Pull Request!
