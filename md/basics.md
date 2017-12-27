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
$a = @(1, 2, 3) # Liste mit den Werten 1,2,3
$a = @{a = 1; b = 2} # Hash Tabelle
$a.b # gibt 2 zurück
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
* `$a += x` entspricht `$a = $a + x`
* Ebenso selbsterklärend wie Arithmetische Operatoren

```ps
$a = 1       # $a = 1
$a += 1      # $a = 2
$s = "Test"  # $s = "Test"
$s *= 2      # $s = "TestTest"
```

---

#### Vergleichs Operatoren

* Vergleichen Dinge & mehr
* Werden in verschiedene Klassen unterteilt
  * Equality
  * Matching
  * Containment
  * Replacement
  * Type

Note:
Zu den Typen Replacement und Matching werde ich nicht viel sagen, da das für den Anfang zu weit führt

---

##### Wichtige Vergleichs Operatoren

```ps
$a -eq $b # $a == $b
$a -ne $b # $a != $b
$a -ge $b # $a >= $b
$a -lt $b # $a <  $b
"Test" -like "Tes*" # True
"Test" -notlike "Test*" # False
@("T", "e", "s", "t") -contains "T" # True
1 -is [int] # True
```

Note:
Der -ge Operator hat noch einen -gt ebenso wie der -gt noch einen -ge Operator hat

Es gibt zum -contains noch die Operatoren -in, -notin, -notcontains

---

#### Logische Operatoren

* Boolesche Operatoren
* `-and`, `-or`, `-xor`, `-not`, `!`
* Vor allem interressant in `if` Abfragen
* Können auch auf nicht Boolesche Werte angewandt werden
* `!` und `-not` machen das selbe

---

##### Wahrheitstabelle

| `$a` | `$b` | `-and` | `-or` | `-xor` |
|:----:|:----:|:------:|:-----:|:------:|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 |

---

#### Umleitungsoperatoren

* Bekannt aus dem `cmd`
* `>`, `>>`, `2>`, `2>>`, `2>&1`
* Leiten die Ausgabe in eine Datei statt sie in der Shell anzuzeigen

---?include=md/basics_redirectiontable.md
