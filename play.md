====
 JS
====

Basis-Typen in JavaScript Strings, Objects, Array, Functions

```javascript
js> funky="grandma"
js> o1 = {"name": "o1"}
js> this
({o1:{name:"o1"}, funky:"grandma"})
js> typeof this
"object"
js> Object.getPrototypeOf(o1)
({})
js> o1.__proto__
({})
js> o1.hasOwnProperty("k")
false
js> o2 = Object.create(o1) // für das Object o2 wird als Muster das Object o2 verwendet
js> o2.name
"o1"
js> o2.__proto__
({name:"o1"})
js> o2.hasOwnProperty("name")
false
js> o2.name = "o2"
js> o2.hasOwnProperty("name")
true
js> o2.name
"o2"
js> delete o2.name
true
js> o2.name
"o1"
```

Funktionen
==========

Versteckte Eigenschaften eines Function-Object
  * prototype
  * Variable-Kontext
  * Funktions Code

Functions Objecte sind mit Function.prototype verknüpft
das weiterhin auf das Object.prototype zeigt.

Jedes Funktions-Objekt besitze eine prototype Eigenschaft mit dem
Namen constructor.

```javascript
js> f = new Function
js> f.prototype.constructor
```

Aufruf Muster von Funktionen zur bestimmung des "this" Wert
  * Methoden:
    Funktion wird innerhalb eines Objekts als Eigenschaft definiert
    "this" wird an Objekt gebunden.
  * Funktions
    Funktion wird nich als Objekt-Eigneschaft definiert "this" 
    wird an das global-Object gebunden. Auch wenn eine Funktion
    innerhalb einer anderen Funktion definiert wird.
  * Konstruktor
    wenn "f = new Funk" aufgerufen wird wird referenziert "this"
    auf Funk außer es wird in Funk durch eine return ein anderes 
    Objekt zurückgegeben. 
  * Apply

Funktionen können innerhalb Funktionen definiert werden diese
Funktionen können dan auf die definierten Variablen innerhalb
der Funktionen zugreifen

```javascript
js> func.call(?)
js> func.apply(this, ?)
```
