# Xifra de Cèsar

Un dels grans comandants militars que feia servir missatges xifrats va ser Juli Cèsar, cap al 50 aC. Feia servir un xifratge senzill conegut com la xifra de Cèsar per protegir les comunicacions militars. Aquest xifratge també es coneix com a xifra per desplaçament, perquè cada lletra del text original es substitueix per una lletra situada un nombre fix de posicions abans o després de l’alfabet.

Per exemple, si escriviu `NIKOLATESLA` i desplaceu cada lletra tres posicions cap a l’esquerra:

![Desplaçament a l’esquerra de la xifra de Cèsar](./images/caesar1.png)

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
```

La lletra `N` es converteix en `K`, la `I` en `F`, i així successivament. Per tant, cada lletra se substitueix per una altra lletra que es troba a una determinada distància dins de l’alfabet.

La **desxifra** funciona de la mateixa manera, però a la inversa. Per desxifrar el text codificat, desplaceu cada lletra tres posicions cap a la dreta:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
```

La lletra `K` es converteix en `N`, la `F` en `I`, i així successivament. El resultat d’aquest desplaçament és el missatge original desxifrat `NIKOLATESLA`.


## Tasca per reflexionar-hi

Penseu com crearíeu una aplicació de consola en qualsevol llenguatge de programació que xifrés i desxifrés missatges mitjançant una xifra de Cèsar.

```{infonote}
El primer estudiant (*programador*) hauria de centrar-se en la sintaxi mentre escriu el codi per xifrar el missatge. El segon estudiant (*navegador*) hauria de seguir el codi, suggerir millores i fer preguntes. Després de xifrar, intercanvieu els rols per desxifrar.
```

L’alfabet permès per als missatges (tant per al text original com per al text xifrat) només pot contenir les lletres minúscules de l’alfabet anglès:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

No es permeten espais, lletres majúscules, números ni altres caràcters.

A la primera línia d’entrada hi ha un missatge `m` de com a màxim cent caràcters; a la segona línia, un enter `n` que representa el valor del desplaçament (1–25), i a la tercera línia, un enter `s` que representa la direcció del xifratge. Si `s=1`, s’ha de xifrar `m`, i si `s=2`, s’ha de desxifrar.

### Exemple de prova 1

Si l’entrada és:

```text
nikolatesla
3
1
```

la sortida hauria de ser:

```text
kfhlixqbpix
```

### Exemple de prova 2

Si l’entrada és:

```text
kfhlixqbpix
3
2
```

la sortida hauria de ser:

```text
nikolatesla
```

## Pistes per a la solució

Com que l’alfabet anglès té 26 lletres, la posició de cada lletra es pot representar amb un número de l’0 al 25.

* a → 0
* b → 1
* c → 2
* ...
* z → 25

Per **xifrar** una lletra, podeu fer servir la fórmula següent:

```text
new_letter_position = (current_letter_position - shift_value + 26) mod 26
```

`current_letter_position` representa el valor numèric de la lletra dins de l’alfabet, `shift_value` representa el nombre de posicions que cal desplaçar (1–25), `+ 26` garanteix que el valor no esdevingui negatiu i `mod 26` garanteix que el valor torni a donar la volta a l’alfabet.

Per **desxifrar** una lletra, podeu fer servir la fórmula següent:

```text
new_letter_position = (current_letter_position + shift_value) mod 26
```

De manera similar al xifratge, però s’hi suma el valor del desplaçament, de manera que el valor no pot esdevenir negatiu i no cal afegir `+ 26`.

## Tasques més complexes amb la xifra de Cèsar (opcional)

### Amplieu l’alfabet permès

Creeu una aplicació de consola en qualsevol llenguatge de programació que xifri i desxifri missatges mitjançant la xifra de Cèsar, però amb un alfabet ampliat.

L’aplicació només ha de xifrar o desxifrar lletres minúscules i majúscules. Els espais, els números i els signes de puntuació han de quedar sense canvis.

A la primera línia d’entrada hi ha un missatge `m` de com a màxim cent caràcters; a la segona línia, un enter `n` (el valor de desplaçament, de l’1 al 25) i a la tercera línia, un enter `s` (1 per al xifratge, 2 per a la desxifra).

## Feu servir les funcions

Creeu dues funcions: una per xifrar missatges i una altra per desxifrar-los. Feu servir les funcions creades al programa principal.

Aquí podeu treballar en parelles: una persona hauria de xifrar el missatge i l’altra, desxifrar-lo!

## Creeu una classe

Creeu una classe `CaesarCipher` que contingui:

- un constructor amb un paràmetre que accepti un valor de desplaçament i garanteixi que el valor estigui dins de l’interval permès (0–25),
- una propietat privada per emmagatzemar el valor de desplaçament, amb els mètodes getter i setter,
- un mètode públic per xifrar un missatge,
- un mètode públic per desxifrar un missatge, i
- opcionalment, un mètode privat per processar missatges que facin servir tots dos mètodes.

Feu servir la classe creada al programa principal.

## Accepteu arguments de la línia de comandos

En lloc d’esperar l’entrada de l’usuari, creeu una aplicació de consola que accepti els arguments següents de la línia de comandos:

1. l’argument `m` per al missatge,
2. l’argument `n` per al valor de desplaçament (`0` a `25`), i
3. l’argument `s` per a la direcció del xifratge (`1` per xifrar, `2` per desxifrar).

## Xifreu i desxifreu fitxers

Feu servir els coneixements adquirits fins ara per crear una aplicació de consola que xifri i desxifri fitxers de text mitjançant la xifra de Cèsar.

L’aplicació ha d’acceptar els arguments següents de la línia de comandos:

1. l’argument `m` per al nom del fitxer (o la ruta),
2. l’argument `n` per al valor de desplaçament (`0` a `25`), i
3. l’argument `s` per a la direcció del xifratge (`1` per xifrar, `2` per desxifrar).
