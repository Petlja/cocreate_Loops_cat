# Escítala

L’escítala (skytale) és una de les eines de xifratge més antigues conegudes; procedeix de l’antiga Grècia, cap al 400 aC. Era un senzill dispositiu cilíndric que els espartans feien servir per enviar missatges secrets durant les campanyes militars.

Una tira de pergamí o de cuir s’enrotllava al voltant d’una vara de fusta (*escítala*) amb un determinat diàmetre. Després, el missatge s’escrivia al llarg de la tira enrotllada. Per desxifrar-lo, el receptor enrotllava la tira al voltant d’una vara del mateix diàmetre i llegia el missatge al llarg, de la mateixa manera com havia estat escrit.

Si voleu xifrar el missatge:

```text
attackatdawn
```

i escolliu una vara que permeti **3 lletres per volta**, la tira hi fa quatre voltes. Escriviu el missatge al llarg de la vara, fila per fila, amb 4 lletres per fila (una a cada volta), i formeu una taula:

```text
a t t a
c k a t
d a w n
```

A continuació, el text xifrat s’obté llegint columna per columna (és l’ordre de les lletres a la tira desenrotllada):

```text
acdtkatawatn
```

Per desxifrar el missatge, el receptor enrotlla la tira al voltant d’una vara del mateix diàmetre i torna a llegir fila per fila per reconstruir el missatge original.

## Primera tasca

Creeu una aplicació de consola en qualsevol llenguatge de programació que xifri i desxifri missatges mitjançant la xifra de l’escítala.

L’alfabet permès per als missatges només conté les lletres minúscules de l’alfabet anglès:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

No es permeten espais, lletres majúscules, números ni altres caràcters!

A la primera línia d’entrada hi ha un missatge `m` de com a màxim cent caràcters. A la segona línia hi ha un enter `k` (el nombre de columnes de la taula per al xifratge). A la tercera línia hi ha un enter `s` (1 per xifrar, 2 per desxifrar).

### Exemple de prova 1

Si l’entrada és:

```text
attackatdawn
4
1
```

la sortida hauria de ser:

```text
acdtkatawatn
```

### Exemple de prova 2

Si l’entrada és:

```text
acdtkatawatn
4
2
```

la sortida hauria de ser:

```text
attackatdawn
```

## Pistes per a la solució

Per al **xifratge**, escriviu el text original fila per fila en una taula amb `k` columnes. Llegiu la taula columna per columna per obtenir el text xifrat.

Per a la **desxifra**, escriviu el text xifrat columna per columna en una taula amb `k` columnes (cada columna conté la longitud del missatge dividida entre `k` lletres) i, després, llegiu la taula fila per fila per reconstruir el text original.

## Tasques més complexes amb l’escítala (opcional)

### Amplieu l’alfabet permès

Incloeu lletres majúscules, espais, números i signes de puntuació.

### Feu servir funcions

Creeu les funcions `encrypt()` i `decrypt()` per modularitzar el codi.

### Creeu una classe

Implementeu una classe `SkytaleCipher` que emmagatzemi `k` i proporcioni mètodes de xifratge i desxifra.

### Xifreu i desxifreu fitxers

Modifiqueu el programa perquè llegiu text original o text xifrat d’un fitxer i escriviu el resultat en un altre fitxer.

### Gestioneu les files incompletes

Modifiqueu el programa perquè, si l’última fila té menys de `k` elements, encara pugui xifrar i desxifrar correctament, gestionant adequadament les files incompletes.
