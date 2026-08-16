# Condicions i bucles

Per seguir amb èxit el material sobre xifratge, cal dominar les idees bàsiques de les condicions i els bucles. Aquests mecanismes permeten que un programa prengui decisions, repeteixi passos i processi text d'una manera controlada. En criptografia, això és essencial: els algoritmes de protecció de dades es basen en regles, comprovacions i repeticions que transformen la informació de forma segura.

Repassem-ne alguns fonaments! Si encara no tens clars aquests conceptes, et recomanem revisar abans les lliçons de Petlja dedicades a aquest tema.

Els diferents tipus de bucles seran útils per a diferents xifratges: de vegades necessitaràs recórrer text caràcter per caràcter, altres vegades repetir passos fins que es compleixi una condició, i en alguns casos combinar bucles i condicions dins del mateix algoritme.

## Enllaços de prerequisits

- [Lliçó de Petlja sobre bucles](https://www.petlja.org/sr-Latn-RS/kurs/477/12/5844)
- [Versió en anglès d'una lliçó introductòria similar](https://petlja.org/en/biblioteka/r/lekcije/python-za-svakog/01_karel_eng_02_for)

```{learnmorenote} Per al professorat

Referències útils per repassar els prerequisits amb l'alumnat:

- Lliçó de Petlja en serbi: https://www.petlja.org/sr-Latn-RS/kurs/477/12/5844
- Versió per a cursos no disponibles en serbi: https://petlja.org/en/biblioteka/r/lekcije/python-za-svakog/01_karel_eng_02_for
```

## Condicions

A la majoria dels llenguatges de programació moderns, les sentències condicionals s'utilitzen per prendre decisions i controlar el flux d'un programa. Les més comunes inclouen:

* if
* if-else
* switch-case

És important notar que tot i que la sintaxi difereix entre llenguatges, la lògica central és la mateixa.

### La sentència `if`

La sentència if executa un bloc de codi només si la condició especificada és veritat.

```text
if condition then
    statement(s)
```

Per exemple, en C, C++, C# i Java, si vols comprovar si `x` és major que `0`, la sentència condicional es pot escriure així:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### La sentència `if-else`

La sentència if-else executa un bloc de codi si la condició és veritat, i un altre bloc si és falsa.

```text
if condition then
    statement(s)
else
    statement(s)
```

Per exemple, en C, C++, C# i Java, si vols comprovar si `x` és major que `0` o no, la sentència condicional es pot escriure així:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### La sentència `switch-case`

La sentència `switch-case` és útil quan es compara la mateixa variable amb molts valors possibles. Pot ser més llegible que usar múltiples sentències `if-else`.

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

Per exemple, en C, C++, C# i Java, si vols determinar el nom del dia basant-se en el seu número ordinal en la setmana, la sentència condicional es pot escriure així:

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

Les sentències condicionals poden col·locar-se dins d'altres sentències condicionals; a això se li diu **anidament**. Les condicions anidades són útils quan una decisió depèn del resultat d'una decisió anterior. Per exemple, primer pots comprovar si un usuari ha iniciat sessió i, dins d'aquest bloc, comprovar si té permís per realitzar una determinada acció.

## Bucles

A la majoria dels llenguatges de programació moderns, els bucles s'implementen habitualment usant una de les següents construccions:

* `for`,
* `while` (o `while-do`),
* `do-while` (o `repeat-until`),
* `foreach` (o `for-each`).

És important notar que tot i que la sintaxi difereix entre llenguatges, la lògica central és la mateixa.

### El bucle `for`

El bucle `for` s'utilitza quan el nombre d'iteracions és finit i predeterminat.

```text
for variable ← start to end do
    statement(s)
```

Per exemple, en C, C++, C# i Java, un bucle `for` per iterar nombres del 0 al 9 es pot escriure així:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### El bucle `while`

El bucle `while` (o `while-do`) s'utilitza quan el nombre d'iteracions no es coneix d'antuvi. La condició es verifica abans de cada iteració, per la qual cosa es coneix com **bucle amb precondició**.

```text
while condition do
    statement(s)
```

Per exemple, en C, C++, C# i Java, un bucle `while` per iterar nombres del 0 al 9 es pot escriure així:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### El bucle `do-while`

El bucle `do-while` (o `repeat-until`) també admet un nombre d'iteracions desconegut, però la condició es verifica després de cada iteració, per la qual cosa es coneix com **bucle amb postcondició**.

```text
repeat
    statement(s)
until condition
```

Per exemple, en C, C++, C# i Java, un bucle `do-while` per iterar nombres del 0 al 9 es pot escriure així:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```

### El bucle `foreach`

El bucle `foreach` (o `for-each`) s'utilitza per iterar a través de tots els elements en una col·lecció o matriu. Aquest tipus de bucle simplifica el codi i redueix la probabilitat d'errors.

```text
for-each element in collection do
    statement(s)
```

Per exemple, un bucle `for-each` per iterar a través d'una matriu `nums` es pot escriure en C++ com:

```cpp
int nums[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

...o en C# així:

```csharp
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
foreach (int i in nums) {
    // ...
}  
```

...o en Java:

```java
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}   
```

### Anidament de bucles

Els bucles també poden estar anidats, la qual cosa significa que un bucle està dins d'un altre. Això és comú quan es treballa amb matrius multidimensionals o quan es necessita realitzar comparacions entre elements.

Els diferents tipus de bucles seran necessaris per a diferents formes de xifratge que aprendràs a les següents pàgines.
