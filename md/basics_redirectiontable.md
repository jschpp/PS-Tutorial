##### Weiterleitungsoperatoren Tabelle

| Operator | Beschreibung                                     | Beispiel                             |
| -------- | ------------------------------------------------ | ------------------------------------ |
| `>`      | Sendet die Ausgabe an eine Datei                 | Get-Process > Process.txt            |
| `>>`     | Hängt die Ausgabe an eine Datei an               | dir *.ps1 >> Scripts.txt             |
| `2>`     | Sendet die Ausgabe des Streams 2 an eine Datei   | Get-Process none 2> Errors.txt       |
| `2>>`    | Hängt die Ausgabe des Streams 2 an eine Datei an | Get-Process none 2>> Save-Errors.txt |
| `2>&1`   | Sendet die Ausgabe des Streams 1 & 2 an Stream 1 | Get-Process none, Powershell 2>&1    |
