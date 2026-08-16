# Xifratge Cèsar

Un dels grans generals que va utilitzar missatges codificats va ser Juli Cèsar, cap al 50
aC. Quan Cèsar enviava missatges als seus generals, els xifrava desplaçant
les lletres del text un nombre fix de posicions a l'alfabet. Els
destinataris del missatge podien desxifrar-lo perquè coneixien el valor de desplaçament
— mentre que tothom altre veia només text sense sentit.

Per exemple, si escrivíeu `NIKOLATESLA` i desplaçàveu cada lletra tres posicions a
la dreta:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
```

La lletra `N` es converteix en `K`, `I` es converteix en `F`, i així successivament. Doncs, cada lletra és
reemplaçada per una altra lletra que es troba un nombre fix de posicions més endavant a
l'alfabet. Quan s'arriba al final de l'alfabet, la seqüència continua
des del principi. El resultat de l'operació de desplaçament de tres lletres a la
dreta seria el missatge xifrat `KFHLIXQBPIX`. D'altra banda, si cada
letra de la paraula resultant es desplacés tres lletres a l'esquerra:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
```

La lletra `K` es converteix en `N`, `F` es converteix en `I`, i així successivament. El resultat de l'operació de desplaçament
seria el missatge desxifrat original `NIKOLATESLA`.

![Desplaçament esquerre del xifratge Cèsar](./images/caesar1.png)

## Assignació simple

Creeu una aplicació de consola en qualsevol llenguatge de programació per xifrar i desxifrar
missatges utilitzant el xifratge Cèsar.

```{infonote}
El primer estudiant (*el pilot*) ha de centrar-se en la sintaxi mentre escriu el
codi per al xifratge de missatges. El segon estudiant (*el navegant*) ha de revisar
cada línia de codi a mesura que s'escriu, buscant errors, fent preguntes
i suggerint millores. Després, els estudiants han d'intercanviar els rols
i continuar escrivint el codi de desxifratge.
```

L'alfabet permès per als missatges (per al text pla i el text xifrat) pot incloure
només lletres minúscules de l'alfabet anglès:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

Els espais, les lletres majúscules, els números i altres caràcters no estan permesos.

A la primera línia de l'entrada de l'usuari hi haurà un missatge `m` de no més de
cent caràcters, a la segona línia hi haurà un enter `n` que
representa el valor de desplaçament ($1 \leq n < 26$), i a la tercera línia hi haurà
un enter `s`, que representa la direcció del xifratge. Si $s=1$, llavors `m`
ha de ser xifrat, i si $s=2$, llavors `m` ha de ser desxifrat.

### Exemple de prova 1

Si l'entrada és:

```text
nikolatesla
3
1
```

la sortida ha de ser:

```text
kfhlixqbpix
```

### Exemple de prova 2

Si l'entrada és:

```text
kfhlixqbpix
3
2
```

la sortida ha de ser:

```text
nikolatesla
```

## Comenceu l'assignació

[Implementeu el xifratge aquí](https://arena.petlja.org/sr-Latn-RS/competition/123-co-create#tab_142923)

## Consells per a la solució

Com que hi ha 26 lletres a l'alfabet anglès, la posició de cada lletra
es pot representar amb un número de 0 a 25.

* a → 0
* b → 1
* c → 2
* ...
* z → 25

Per **xifrar** una lletra, podeu utilitzar la fórmula següent:

```text
new_letter_position = (current_letter_position + shift_value) mod 26
```

`original_position` representa el valor numèric de la lletra a l'alfabet,
`shift_value` representa el nombre de posicions a moure (1–25), i `mod 26`
assegura que el resultat torni al principi de l'alfabet si supera `z`.

Per **desxifrar** una lletra, podeu utilitzar la fórmula següent:

```text
new_letter_position = (current_letter_position - shift_value + 26) mod 26
```

De manera similar al xifratge, però es resta el valor de desplaçament, i `+ 26` assegura
que el valor no es torni negatiu abans d'aplicar `mod 26`.

## Assignacions avançades del xifratge Cèsar (opcionals)

### Amplieu l'alfabet permès

Creeu una aplicació de consola en qualsevol llenguatge de programació per xifrar i desxifrar
missatges utilitzant el xifratge Cèsar. L'alfabet permès per als missatges (per al
text pla i el text xifrat) pot incloure lletres minúscules i majúscules de
l'alfabet anglès, espais, números i puntuació!

L'aplicació ha de xifrar o desxifrar només lletres minúscules i majúscules.
Els espais, els números i els signes de puntuació han de romandre sense canvis durant
el xifratge o el desxifratge.

A la primera línia de l'entrada estàndard hi haurà un missatge `m` de no més
de cent caràcters, a la segona línia hi haurà un enter `n`
que representa el desplaçament ($1 \leq n < 26$), i a la tercera línia hi haurà
un enter `s`, que representa la direcció del xifratge. Si $s=1$ llavors `m`
ha de ser xifrat, i si $s=2$, llavors `m` ha de ser desxifrat.

## Utilitzeu les funcions

Creeu dues funcions: una per xifrar missatges i una per desxifrar
missatges. Utilitzeu les funcions creades al vostre programa principal.

## Creeu una classe

Creeu una classe `CaesarCipher` que contingui:

* un constructor amb un paràmetre que accepti el valor de desplaçament i asseguri que
el valor estigui dins del rang permès,
* una propietat privada per emmagatzemar el valor de desplaçament, amb mètodes getter i setter,
* un mètode públic per xifrar el missatge,
* un mètode públic per desxifrar el missatge, i
* opcionalment, incloeu un mètode privat per processar missatges, que serà utilitzat
tant pels mètodes de xifratge com de desxifratge.

Utilitzeu la classe creada al vostre programa principal.

## Accepteu arguments de la línia d'ordres

En lloc d'esperar l'entrada de l'usuari, creeu una aplicació de consola que
accepti els arguments de la línia d'ordres següents:

1. argument `m` per especificar el missatge,
2. argument `n` per especificar el valor de desplaçament (`0` a `25`), i
3. argument `s` per especificar la direcció del desplaçament (`1` per al xifratge, i `2`
per al desxifratge).

## Xifreu i desxifreu fitxers

Utilitzeu els coneixements adquirits fins ara per crear una aplicació de consola per
xifrar i desxifrar fitxers de text. La vostra aplicació ha d'acceptar els arguments de la
línia d'ordres següents:

1. argument `m` per especificar el nom del fitxer (o una ruta),
2. argument `n` per especificar el valor de desplaçament (`0` a `25`), i
3. argument `s` per especificar la direcció del desplaçament (`1` per al xifratge, i `2`
per al desxifratge).
