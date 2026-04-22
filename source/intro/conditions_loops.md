# Condicions i bucles

Per dominar amb èxit el material de la lliçó següent, cal conèixer
els fets bàsics sobre el treball amb condicions i bucles.

## Condicions

En la majoria dels llenguatges de programació moderns, les instruccions condicionals s'utilitzen per prendre
decisions i controlar el flux d'un programa. Les construccions més comunes són:

* if
* if-else
* switch-case

Tot i que la sintaxi difereix entre els llenguatges, la lògica central és la mateixa.

### La instrucció `if`

La instrucció `if` executa un bloc de codi només si una condició especificada és
certa.

```text
if condition then
    statement(s)
```

Per exemple, en C, C++, C# i Java, si voleu comprovar si `x` és més gran que
`0`, la instrucció condicional es pot escriure com:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### La instrucció `if-else`

La instrucció if-else executa un bloc de codi si la condició és certa, i
un altre bloc si és falsa.

```text
if condition then
    statement(s)
else
    statement(s)
```

Per exemple, en C, C++, C# i Java, si voleu comprovar si `x` és més gran que
`0` o no és més gran que `0`, la instrucció condicional es pot escriure com:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### La instrucció `switch-case`

La instrucció `switch-case` és útil quan es compara la mateixa variable amb
molts valors possibles. Pot ser més llegible que utilitzar moltes instruccions
`if-else`.

```text
switch expression do
    case value1:
        statement(s)
    case value2:
        statement(s)
    ...
    default:
        statement(s)
```

Per exemple, en C, C++, C# i Java, si voleu determinar el nom del
dia en funció del seu número ordinal a la setmana, la instrucció condicional es pot
escriure com:

```csharp
int day = 3;
string name = "";
switch (day) {
    case 1:
        name = "Monday";
        break;
    case 2:
        name = "Tuesday";
        break;
    case 3:
        name = "Wednesday";
        break;
    // ...
    default:
        name = "";
        break;
}
```

### Anidament de condicions

Les instruccions condicionals es poden col·locar dins d'altres instruccions condicionals; això
es diu **anidament**. Les condicions anidades són útils quan una decisió depèn del
resultat d'una decisió anterior. Per exemple, podríeu comprovar primer si un usuari
ha iniciat sessió i, a continuació, dins d'aquest bloc, comprovar si té permís per
realitzar una determinada acció.

## Bucles

En la majoria dels llenguatges de programació moderns, els bucles s'implementen habitualment utilitzant una
de les construccions següents:

* `for`,
* `while` (or `while-do`),
* `do-while` (or `repeat-until`),
* `foreach` (or `for-each`).

Tot i que la sintaxi difereix entre els llenguatges, la lògica central és la mateixa.

### El bucle `for`

El bucle `for` s'utilitza quan el nombre d'iteracions és finit i
predeterminat.

```text
for variable ← start to end do
    statement(s)
```

Per exemple, en C, C++, C# i Java, un bucle `for` per iterar pels nombres
del 0 al 9 es pot escriure com:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### El bucle `while`

El bucle `while` (o `while-do`) s'utilitza quan el nombre d'iteracions és
desconegut d'antuvi. La condició es comprova abans de cada iteració, per la qual cosa
aquest s'anomena **bucle amb precondició**.

```text
while condition do
    statement(s)
```

Per exemple, en C, C++, C# i Java, un bucle `while` per iterar pels nombres
del 0 al 9 es pot escriure com:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### El bucle `do-while`

El bucle `do-while` (o `repeat-until`) també admet un nombre desconegut
d'iteracions, però la condició es comprova després de cada iteració. Això s'anomena
**bucle amb postcondició**, i sempre s'executa almenys una vegada.

```text
repeat
    statement(s)
until condition
```

Per exemple, en C, C++, C# i Java, un bucle `do-while` per iterar pels
nombres del 0 al 9 es pot escriure com:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```

### El bucle `foreach`

El bucle `foreach` (o `for-each`) s'utilitza per iterar sobre tots els elements d'una
col·lecció o matriu. Simplifica la iteració quan no cal conèixer
l'índex.

```text
for-each element in collection do
    statement(s)
```

Per exemple, un bucle `for-each` per iterar per la matriu `nums` es pot escriure
en C++ com:

```cpp
int nums[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

...o en C# com...

```csharp
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
foreach (int i in nums) {
    // ...
}  
```

...o en Java com:

```java
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}   
```

### Anidament de bucles

Els bucles també es poden anidar, és a dir, un bucle es col·loca dins d'un altre. Això
és comú quan es treballa amb dades multidimensionals, com ara recórrer files i
columnes d'una matriu o iterar sobre una quadrícula en un joc. A més, els bucles i
les condicions es poden combinar lliurement — per exemple, un bucle pot contenir una instrucció
`if` per processar només certs elements, o una instrucció `if` pot contenir un
bucle per realitzar accions repetides quan una condició és certa. Aquesta capacitat de barrejar
i anidar bucles i condicions permet la creació d'algoritmes complexos
mantenint la lògica subjacent estructurada.
