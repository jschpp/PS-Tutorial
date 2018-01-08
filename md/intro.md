## Was ist Powershell

Powershell ist eine von Microsoft entwickelte Scriptsprache zum Management von Windows Server und Clients.

Sie basiert auf dem .net Framework und wird als Teil des Windows Management Frameworks ausgeliefert.

Seit August 2016 ist Powershell **Core** unter Linux und Mac verfügbar.

---?code=src/examples/simple-script.ps1&lang=powershell&title=Ein einfaches Powershell Programm

Ausgabe:

```console
Hello World
Lauf 1
Lauf 2
Lauf 3
Lauf 4
Lauf 5
```

---

### Was ist das .net Framework

* Laufzeitumgebung (.NET Common Language Runtime)
* Beinhaltet Standard Funktionen und Klassen
  * Windows Forms
  * Windows Presentation Foundation (WPF)
* ist zumindest teilweise auch unter Unix verfügbar
* Kann aus der Powershell direkt angesprochen werden

Note:
Unter einer Laufzeitumgebung versteht man eine Ausführungsumgebung die die zur Laufzeit verfügbaren Vorraussetzungen eines Laufzeitsystems (wikipedia)

Darin werden unter anderem definiert wie das

* Lesen und schreiben von Dateien
* Daten über Netzwerke transportieren
* Ein- und Ausgabegeräte steuern
* Daten verwalten
* Sortieren und Suchen

funktioniert

Quelle: [wikipedia](https://de.wikipedia.org/wiki/Laufzeitumgebung)

---

### Warum Powershell

* Viele Aufgaben im täglichen IT Alltag können damit automatisiert werden
* Bestimmte Funktionalitäten sind jetzt schon nur mit Powershell erreichbar

---

### Die Werkzeuge der Powershell

* Powershell Konsole
* Powershell ISE (Integrated Scripting Enviroment)
* Belieber Texteditor/IDE

In diesem Kurs verwenden wir ausschließlich die ISE sowie die Native Konsole

---

### Was automatisieren mit Powershell

* Windows (Server)
* Active Directory
* Azure
* Sharepoint
* Office 365
* Echange
* SQL
* SCCM

---

### Systemvorraussetzungen

Für Powershell v5

* Ab Windows 7 ab SP1 / Server 2008 R2 mit SP1
* .net Framework 4.5
