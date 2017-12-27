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

Ein Alias ist ein anderer Name für ein Funktion oder ein cmdlet

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

---

## Quellen

Powershell Verfügbarkeit [https://blogs.msdn.microsoft.com/powershell/2016/08/18/powershell-on-linux-and-open-source-2/](https://blogs.msdn.microsoft.com/powershell/2016/08/18/powershell-on-linux-and-open-source-2/)

Gültige Powershell Verben: [https://msdn.microsoft.com/en-us/library/ms714428%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396](https://msdn.microsoft.com/en-us/library/ms714428%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396)
