# Grundlagen der Programmierung 
##  Ablaufplan
> Ein Programmablaufplan (PAP) ist eine grafische Darstellung zur Umsetzung eines Algorithmus in einem Programm. 
> 
![Beispiel PAP](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Flowchart_de.svg/800px-Flowchart_de.svg.png =300x500)

<br>

## einfache Variablen und deren Wertebereiche

>Dies sind die vorhandenen Datentypen und deren Wertebereich in C#

| Datentype | Wertebereich |
| --------- | ------------ |
|int | -2^31 bis 2^31
|double | -1,7•10^308 bis 1,7•10,308
|long|-2^63 bis 2^63
|float|1,0239846E-45f bis 3,40282347E+38f
|short | -32768 bis 32767
|byte| -128 bis 127
|char | 1 Zeichen
|boolean | true/false
|String | Text |

## Gültigkeit von Variablen / Blöcke

### Warum Wir 'const' oder 'let' benutzen anstatt 'var'
>*Früher hat man mit "var" variabeln deklariert, da es keine alternativen damals gab. Heute sieht es anders aus. Heute, bzw. seit ES6 gibt es "const" und "let", warum wir nicht mehr "var" benutzen liegt daran, dass es vor ES6 keine **block scopes** gab, sondern nur **function scopes.** Ebenfalls werden die Begriffe **lokale** und **globale Variabeln** als Nächstes erklärt.* 

### <br>Block scope

> Variabeln die in einem Block deklariert werden sind auch nur innerhalb des Blockes aufrufbar. <br> <br>Hier ein Beispiel dazu:
```js
let arr = ['Apfel', 'Kiwi', 2, 101912, 'Banane', 91]
    for (let i = 0; i < arr.length; i++){
        console.log(arr[i]);}

Output: 
'Apfel'
'Kiwi'
2
101912
'Banane'
91
```
>Würde man jetzt die Variabel *i* Ausgeben wollen (außerhalb der Schleife) mit
```js
console.log(i);
```
>würde man folgenden fehler kriegen:<br>

<div class = "Farbe", style=background-color:rgba(253,60,60,0.5)> Uncaught ReferenceError: i is not defined </div>
<br>

>Die Variabel *i* wurde im Block deklariert mit einem *let*, was schon vorher angesprochen wurde. *let* deklariert die Variabel im *Block bzw. lokal*. Wenn man das *let* hingegen weglässt deklariert man die Variabel *global*, dementsprechend würde die Fehlermeldung nicht mehr erscheinen und man würde die Zahl *6* ausgegeben bekommen.

<br>

### Function Scope 
>Beim Function Scope ist es etwas anders als beim Block Scope. Beim Function Scope ist die Variabel die man definiert in der ganzen Funktion aufrufbar und nicht nur im Block, selbst bei einer For-Schleife. <br> <br>
Hier das Beispiel:
```js
let arr = ['Apfel', 'Kiwi', 2, 101912, 'Banane', 91]
function FunctionScope (arr) {
    for(var i = 0; i < arr.length; i++)
        {
            console.log(arr[i]);
        } 
    console.log('Ich kann die variabel i auch hier benutzen ', i);
    }
FunctionScope(arr);
```
> Die Variabel *i* kann nun auch außerhalb der For-Schleife aufgerufen werden, da es sich in einer Funktion befindet.

<br>


### Grundlegende Anweisung (if,- for schleife, switch)

>Grundlegende Anweisungen wie If-else Anweisung, for schleifen,switch, oder do while Statements sind in der Programmierung nicht wegzudenken. Als Nächstes folgt jeweils ein Beispiel zu den genannten Anweisungen.

### ***If-else schleife***

>Die If-Anweisung führt eine Anweisungen aus, wenn die Bedingung ```true``` ist. Wenn die Bedingung ```false``` ist, wird das was in ```else``` Anweisung steht ausgeführt. 
<br> So sieht eine If...else Anweisung aus:

```js
let a = 1

if (a > 0) {
    console.log("a ist größer als 0")
} else {
    console.log("a ist nicht größer als 0")
}
Output: "a ist größer als 0"

```

>Die Variabel a wurde auf 1 deklariert dementsprechend wird das ausgegeben was in dem If Berreich steht und nicht was im else steht.

### ***For schleife***

>Die for Anweisung beschreibt eine Schleife mit drei optionalen Ausdrücken und einer oder mehreren Anweisungen. Im obrigen Beispiel zum Thema Function Scope sieht man den Grudaufbau einer for schleife. Es gibt mehrere variation von For schleifen (z.B for await...of, for...in etc.) die werden wir nicht erklärt, weil es sich hier um die Grundlagen handelt.

### ***Switch***
>Die switch Anweisung wertet einen Ausdruck aus. Diese Auswertung wird mit einer case Klausel verglichen und (bei Übereinstimmung) die entsprechenden Anweisungen ausgeführt.
<br>
Hier ein Beispiel:

```js
let Tag = "Montag"

switch (Tag) {
  case "Montag" :
    console.log("Es ist Montag");
    break;
  case "Dienstag":
    console.log("Es ist Dienstag");
    break;
  case "Mittwoch":
    console.log("Es ist Mittwoch");
    break;
  case "Donnerstag":
    console.log("Es ist Donnerstag");
    break;
  case "Freitag":
    console.log("Es ist Freitag");
    break;
  case "Samstag":
    console.log("Es ist Samstag");
    break;
  case "Sonntag":
    console.log("Es ist Sonntag");
    default:
    console.log("Es ist kein Tag");
}
```
>In unserem Beispiel haben wir einer Variabel mit dem Namen "Tag“ den Wert "Montag" zugewiesen. Somit wird der erste case "Montag" ausgeführt. Beim ```default``` ist es so, dass er ausgeführt wird, wenn keins der cases zutreffen.

### Zielsysteme
