Obwohl Siemens ein deutsches Unternehmen ist kann man im LWE nur das Format YYYY-MM-DD auswählen. Um das Datum im Format DD-MM-YYYY anzuzeigen muss ein bisschen was in der \js\render.js Datei verändert werden. Hier können auch die Abkürzungen der Wochentage angepasst werden. 

Alle Zeilenangaben sind auf [ Notepad++](https://notepad-plus-plus.org/) bezogen. 

\js\render.js in Notepad++ öffnen.

Zeile 8: var WEEKDAY = new Array("Sun.", "Mon.", "Tues.", "Wed.", "Thur.", "Fri.", "Sat."); 

Hier werden die Abkürzungen der Wochentage in das Array WEEKDAY geschrieben. Die Tage einfach ins deutsche übersetzen.

Zeile 8: var WEEKDAY = new Array("So.", "Mo.", "Di.", "Mi.", "Do.", "Fr.", "Sa."); 

Ab der Zeile 1626 beginnt die Funktion, die das Datum zurück gibt.

Wir beginnen ab Zeile 1628. Hier wird das Datum/Uhrzeit in die Variable "sv" geschrieben und in den folgenden Zeilen aufgeteilt (date,time,dayNo) bzw. zusammengebaut.

Zeile 1631: var date = "20" + sv.substr(2, 2) + " - " + sv.substr(4, 2) + " - " + sv.substr(6, 2);

Die "20" ist statisch, das Jahr steht an der 2 Stelle in der Variable "sv" und hat 2 Zeichen, Monat an 4 Stelle und hat 2 Zeichen und der Tag an 6 Stelle wieder 2 Zeichen.

Die Reihenfolge ändern wir dann in:

Zeile 1631: var date = sv.substr(6, 2) + "-" + sv.substr(4, 2) + "-" + "20" + sv.substr(2, 2);

Die veränderte \js\render.js Datei auf die SD-Karte packen und fertig.
