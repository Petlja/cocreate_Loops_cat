# XOR

XOR *(OR exclusiu)* és una operació lògica que produeix cert (1) només quan
les entrades difereixen. És una operació binària fonamental amb importants aplicacions
en informàtica i criptografia.

| A | B | A XOR B |
| - | - | :-----: |
| 0 | 0 | 0       |
| 0 | 1 | 1       |
| 1 | 0 | 1       |
| 1 | 1 | 0       |

Per exemple, per xifrar la paraula "HELLO" utilitzant la clau "KEY", primer heu de
convertir `HELLO` a binari...

| Char | ASCII | Binary   |
| ---- | ----- | -------- |
| H    | 72    | 01001000 |
| E    | 69    | 01000101 |
| L    | 76    | 01001100 |
| L    | 76    | 01001100 |
| O    | 79    | 01001111 |

...després convertiu `KEY` a binari...

| Char | ASCII | Binary   |
| ---- | ----- | -------- |
| K    | 75    | 01001011 |
| E    | 69    | 01000101 |
| Y    | 89    | 01011001 |

...i finalment feu el xifratge - XOR de cada caràcter amb la clau, repetint la
clau tantes vegades com sigui necessari:

```text
H ⊕ K: 01001000 ⊕ 01001011 = 00000011 (ASCII 3)
E ⊕ E: 01000101 ⊕ 01000101 = 00000000 (ASCII 0)
L ⊕ Y: 01001100 ⊕ 01011001 = 00010101 (ASCII 21)
L ⊕ K: 01001100 ⊕ 01001011 = 00000111 (ASCII 7)
O ⊕ E: 01001111 ⊕ 01000101 = 00001010 (ASCII 10)
```

El text xifrat resultant consisteix en caràcters ASCII no imprimibles amb
valors decimals 3, 0, 21, 7 i 10. Si un atacant interceptés aquest missatge,
només veuria dades binàries il·legibles, ja que els caràcters no són
imprimibles.

Per desxifrar el text xifrat heu de fer XOR del text xifrat amb la mateixa clau:

```text
3  ⊕ K: 00000011 ⊕ 01001011 = 01001000 (ASCII 72 → H)
0  ⊕ E: 00000000 ⊕ 01000101 = 01000101 (ASCII 69 → E)
21 ⊕ Y: 00010101 ⊕ 01011001 = 01001100 (ASCII 76 → L)
7  ⊕ K: 00000111 ⊕ 01001011 = 01001100 (ASCII 76 → L)
10 ⊕ E: 00001010 ⊕ 01000101 = 01001111 (ASCII 79 → O)
```

L'operació XOR és autoinversa — aplicar XOR dues vegades amb la mateixa clau
restaureix les dades originals.

En aplicacions del món real, reutilitzar la mateixa clau per a múltiples missatges fa que
el xifratge XOR sigui vulnerable a l'anàlisi de freqüència i als atacs de text pla conegut.
El XOR sol no proporciona una seguretat forta tret que la clau s'administri adequadament
i sigui almenys tan llarga com el missatge — com en un bloc d'un sol ús. No obstant això, per a
propòsits educatius i demostracions bàsiques de principis criptogràfics, XOR
és simple i ideal.

## Assignació simple

Creeu una aplicació de consola en qualsevol llenguatge de programació per xifrar i desxifrar
missatges utilitzant l'operació XOR.

L'alfabet permès per als missatges (tant per al text pla com per a la clau) inclou només
lletres angleses minúscules:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

Els espais, les lletres majúscules, els números i altres caràcters no estan permesos.

A la primera línia de l'entrada de l'usuari hi haurà un missatge `m` de no més de
cent caràcters ASCII per al text pla o 800 bits per al text xifrat, a la
segona línia hi haurà una clau `k` de no més de cinc caràcters, i a la
tercera línia hi haurà un enter `s`, que representa l'operació. Si
$s=1$ llavors `m` és text pla i ha de ser xifrat, i si $s=2$, llavors `m` és
text xifrat en binari i ha de ser desxifrat.

### Exemple de prova 1

Si l'entrada és:

```text
nikolatesla
ser
1
```

la sortida ha de ser:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
```

### Exemple de prova 2

Si l'entrada és:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
ser
2
```

la sortida ha de ser:

```text
nikolatesla
```

## Comenceu l'assignació

[Implementeu el xifratge aquí](https://arena.petlja.org/sr-Latn-RS/competition/123-co-create#tab_142947)

## Consells per a la solució

Cada caràcter s'emmagatzema en memòria com un valor ASCII de 8 bits (per a les lletres
minúscules a–z, els codis van del 97 al 122). Per xifrar un caràcter, preneu el seu
valor ASCII i el valor ASCII del caràcter de clau corresponent (ciclant
pel conjunt de la clau), apliqueu XOR (^) entre ells i produïu el resultat com un número binari de 8 bits.

Per desxifrar, seguiu el procés invers: preneu cada bloc binari de 8 bits del
text xifrat, convertiu-lo de nou a un enter (0–255), feu XOR amb el valor ASCII del
caràcter de clau corresponent i convertiu el resultat de nou a un caràcter.

## Assignacions avançades de XOR (opcionals)

### Amplieu l'alfabet permès

Permeteu lletres minúscules i majúscules, espais, números i puntuació.
Els caràcters que no són lletres es fan XOR amb la clau de la mateixa manera.

## Utilitzeu funcions

Creeu dues funcions: `encrypt()` per xifrar missatges i `decrypt()` per
desxifrar missatges. Utilitzeu les funcions creades al vostre programa principal.

### Creeu una classe

Creeu una classe `XorCipher` que:

* Emmagatzemi la clau,
* Proporcioni mètodes `encrypt()` i `decrypt()`,
* Opcionalment inclogui un auxiliar privat per repetir la clau sobre la longitud del missatge.

Utilitzeu la classe creada al vostre programa principal.

### Accepteu arguments de la línia d'ordres

En lloc d'esperar l'entrada de l'usuari, creeu una aplicació de consola que
accepti els arguments de la línia d'ordres següents:

1. argument `m` per especificar el missatge,
2. argument `k` per especificar la clau, i
3. argument `s` per especificar l'operació (`1` per xifrar, `2` per desxifrar).

### Xifreu i desxifreu fitxers

Utilitzeu els coneixements adquirits fins ara per crear un programa que pugui:

* llegir text pla o text xifrat binari d'un fitxer,
* xifrar-lo o desxifrar-lo amb una clau donada, i
* escriure el resultat en un nou fitxer.
