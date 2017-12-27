# Powershell Schulung

### Eine Schulung über die Verwendung von Powershell in Windows Umgebungen

---

## Was ist Powershell

Powershell ist eine von Microsoft entwickelte Scriptsprache zum Management von Windows Server und Clients.

Sie basiert auf dem .net Framework und wird als Teil des Windows Management Frameworks ausgeliefert.

Seit August 2016 ist Powershell **Core** auch unter Linux und Mac verfügbar

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

## Grundbegriffe

* Cmdlet
* Parameter
* Alias
* Function
* Variable
* Module
* Snapin
* Provider
* Operatoren

---

### Cmdlet

* Wird command-let ausgesprochen
* Sind in .net kompilierte Befehle
* Folgt einer Verb-Nomen Namensgebung
  * Gültige Verben finden sich im Netz (Siehe Quellen)
* Das Nomen bezieht sich aus das zu bearbeitene "Ding" (z.B. Service, ADUser)

Beispiel:

```ps
Get-Service
```

---

### Parameter

* Sowohl bei Funktionen als auch bei cmdlets vorhanden
* Können optional sein
* Können sowohl namentlich als auch über ihre Position verwendet werden

Beispiel

```ps
Get-Help Get-Service
Get-Help -Name Get-Service
Get-Help Get-Service -online
Get-Help -Name Get-Service -full
```

---

### Alias

Ein Alias ist ein anderer Name für eine Funktion oder ein cmdlet

Beispiele:

```ps
man
Get-Help

ps
Get-Process

ft
Format-Table
```

---

### Function

* Modularer wiederverwendbarer Block Code
* Arbeitet ähnlich wie ein cmdlet ist aber in Powershell Script geschrieben
* Können in ein Module ausgelagert werden

---?code=src/examples/simple-function.ps1&lang=powershell&title=Ein einfache Beispiel Funktion

---

### Variable

* Da um Dingen einen Namen zu geben
* Beginnt mit einem $ Zeichen
* Sollten camelCase benannt werden
* Sollten (Wie in jeder anderen Sprache auch) einen _aussagekräftigen_ Namen haben

Beispiele:

```ps
$a = 1
$serviceNames = Get-Service | Select-Object Name
```

---

### Module

* Eine Sammlung von Powershell Befehlen
* Häufig an Windows Produkte oder Features gebunden
* Können als Binär Datei vorliegen
* Sind gut um Funktions Sammlungen nach Funktionalität gebündelt abzulegen
* Werden seit Powershell v4 automatisch geladen

---

#### Wichtige Befehle für Module

```ps
Get-Module # Zeigt alle aktuell geladen Module
Get-Module -ListAvailable # Zeigt alle verfügbaren Module
Get-Command -Module Name # Zeigt alle Befehle des Moduls
Import-Module Name # Lädt ein Modul
Remove-Module # Enlädt ein Modul
```

---

### Snapin

* Ähnlich wie ein Modul
* Liegen kompiliert vor
* Enthalten cmdlets
* Werden in der Regel mit einem Produkt (Exchange, Veeam, ...) mitgeliefert
* Müssen installiert werden
* Sind die "alte" Variante um Funktionen zu bündeln

---

### Provider

* Stellen eine Datenschnittstelle dar
* Daten werden wie ein Laufwerk angezeigt
* Sollen ermöglichen, dass Daten auf eine konsistente Art verfügbare gemacht werden

---?code=src/examples/provider.ps1&lang=powershell&title=Provider Beispiele

---

### Operators

* Machen Dinge :)
* Verschiedene Arten von Operatoren
  * Arithmetische
  * Zuweisungs
  * Vergleichs
  * Logische
  * Umleitungs
  * Typen
  * Spezielle

---

#### Arithmetische Operatoren

* Werden verwendet um Dinge zu berechnen
* `+`, `-`, `*`, `/`, `%`
* Selbsterklärend in den meisten Fällen
* `%` ist der Modulo Operator (Teilen mit Rest)
* Funktionieren nicht nur mit Zahlen.

```ps
"Test" + "2" # "Test2"
"Test" - "2" # Fehler
"Test" * "2" # "TestTest"
"Test" / "2" # Fehler
"Test" % "2" # Fehler
```

---

#### Zuweisungs Operatoren

* Werden verwendet um Variablen neue Werte zuzuweisen
* `=`, `+=`, `-=`, `*=`, `/=`, `%=`
* Ebenso selbsterklärend wie Arithmetische Operatoren

```ps
$a = 1       # $a = 1
$a += 1      # $a = 2
$s = "Test"  # $s = "Test"
$s *= 2      # $s = "TestTest"
```

---
## Quellen

Zu finden unter

[https://github.com/jschpp/PS-Tutorial/blob/master/sources.md](https://github.com/jschpp/PS-Tutorial/blob/master/sources.md)
