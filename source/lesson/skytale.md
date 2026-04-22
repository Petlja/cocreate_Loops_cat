# Escítala

Després de completar aquesta lliçó, sereu capaços de:

* Explicar com funciona el xifratge Escítala.
* Implementar el xifratge i el desxifratge utilitzant operacions simples de matrius o cadenes.
* Comprendre com els dispositius de xifratge físics es poden modelar digitalment.

L'Escítala és una de les eines de xifratge més antigues conegudes, que data de
l'antiga Grècia cap al 400 aC. Era un dispositiu cilíndric simple utilitzat pels
espartans per enviar missatges secrets durant les campanyes militars.

Una tira de pergamí o cuir s'enrotllava al voltant d'una vareta de fusta (l'*escítala*)
d'un diàmetre específic. El missatge s'escrivia longitudinalment al llarg de la vareta.
Un cop desenrotllades, les lletres apareixien barrejades i sense sentit. El destinatari
necessitava una vareta del **mateix diàmetre exacte** per embolcallar la tira i llegir el
missatge original.

Si voleu xifrar el missatge:

```text
attackatdawn
```

i trieu una vareta que permet **4 lletres per volta**, primer escriviu el
missatge verticalment en columnes, formant files de longitud 4:

```text
a t t a
c k a t
d a w n
```

El text xifrat es crea llegint fila per fila:

```text
acdtkatawatn
```

Per desxifrar, el receptor torna a enrotllar la tira al voltant d'una vareta del mateix diàmetre
i llegeix verticalment de nou per reconstruir el missatge original.

## Assignació simple

Creeu una aplicació de consola en qualsevol llenguatge de programació per xifrar i desxifrar
missatges utilitzant el xifratge Escítala.

L'alfabet permès per als missatges inclou només les lletres minúscules de
l'alfabet anglès:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

Els espais, les lletres majúscules, els números i altres caràcters no estan permesos.

A la primera línia de l'entrada de l'usuari hi haurà un missatge `m` de no més de
cent caràcters. A la segona línia hi haurà un enter `k` (el
nombre de columnes – circumferència de la vareta). A la tercera línia hi haurà
un enter `s`, que representa l'operació. Si $s=1$, llavors `m` ha de ser
xifrat. Si $s=2$, llavors `m` ha de ser desxifrat.

### Exemple de prova 1

Si l'entrada és:

```text
attackatdawn
4
1
```

la sortida ha de ser:

```text
acdtkatawatn
```

### Exemple de prova 2

Si l'entrada és:

```text
acdtkatawatn
4
2
```

la sortida ha de ser:

```text
attackatdawn
```

## Comenceu l'assignació

[Implementeu el xifratge aquí](https://arena.petlja.org/sr-Latn-RS/competition/123-co-create#tab_142946)

## Consells per a la solució

Per al **xifratge**, escriviu el text pla verticalment en una taula amb `k`
columnes. Llegiu la taula fila per fila per formar el text xifrat. Per al **desxifratge**,
escriviu el text xifrat fila per fila en una taula amb `k` columnes, llegiu la taula
verticalment per reconstruir el text pla.

## Assignacions avançades de l'Escítala (opcionals)

### Amplieu l'alfabet permès

Incloeu lletres majúscules, espais, números i puntuació.

### Utilitzeu funcions

Creeu funcions `encrypt()` i `decrypt()` per mantenir el codi modular.

### Creeu una classe

Implementeu una classe `SkytaleCipher` que emmagatzemi `k` i proporcioni mètodes per
al xifratge i el desxifratge.

### Xifreu i desxifreu fitxers

Modifiqueu el programa per llegir text pla o text xifrat d'un fitxer i escriure
els resultats en un altre fitxer.

### Gestioneu files incompletes

Modifiqueu el vostre programa de manera que si l'ultima fila és més curta que `k`, encara
xifri i desxifri correctament gestionant els caràcters que falten o el farciment.
