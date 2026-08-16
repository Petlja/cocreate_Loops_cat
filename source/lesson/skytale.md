# Skytale

Skytale (angl. skytale) és una de les eines de xifratge més antigues que es coneixen, i prové de l'antiga Grècia cap al 400 aC. Era un dispositiu cilíndric senzill que els espartans utilitzaven per enviar missatges secrets durant les campanyes militars.

Una cinta de pergamí o pell es enrotllava al voltant d'un petit bastó de fusta (*skytale*) d'un diàmetre determinat. El missatge es escrivia al llarg del bastó. Quan la cinta es desenrotllava, les lletres semblaven barrejades i sense sentit. El receptor havia de tenir un bastó amb el **mateix diàmetre** per poder enrotllar la cinta i llegir el missatge original.

Si vols xifrar un missatge:

```text
attackatdawn
```


i triïs un bastó que permet **4 lletres per volta**, primer escrius el missatge verticalment en columnes, formant files de longitud 4:

```text
a t t a
c k a t
d a w n
```


El text xifrat es genera llegint per files:

```text
acdtkatawatn
```


Per desxifrar el missatge, el receptor enrotlla de nou la cinta al voltant del bastó del mateix diàmetre i llegeix verticalment per reconstruir el missatge original.


## Primer exercici

Crea una aplicació de consola en qualsevol llenguatge de programació que xifri i desxifri missatges utilitzant el xifratge Skytale. Utilitza l'entorn de desenvolupament que feu servir a les classes de programació.

L'alfabet permès per als missatges conté només lletres minúscules de l'alfabet anglès:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```


No es permeten espais, majúscules, nombres ni altres caràcters!


A la primera línia de l'entrada hi ha un missatge `m` de longitud com a molt cent caràcters. A la segona línia hi ha un nombre enter `k` (nombre de columnes: circumferència del bastó). A la tercera línia hi ha un nombre enter `s` que representa l'operació. Si $s=1$, llavors s'ha de xifrar `m`. Si $s=2$, llavors s'ha de desxifrar `m`.


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

## Consells per resoldre-ho

Per a **xifrar**, escriu el text obert verticalment en una taula amb `k` columnes. Llegeix la taula per files per obtenir el text xifrat. Per a **desxifrar**, escriu el text xifrat per files en una taula amb `k` columnes i després llegeix la taula verticalment per reconstruir el text obert.


## Exercicis més avançats amb el xifratge Skytale (opcional)

### Amplia l'alfabet permès

Inclou majúscules, espais, nombres i signes de puntuació.

### Fes servir funcions

Crea funcions `encrypt()` i `decrypt()` perquè el codi sigui modular.

### Crea una classe

Implementa la classe `SkytaleCipher` que emmagatzemi `k` i ofereixi mètodes per xifrar i desxifrar.

### Xifra i desxifra fitxers

Modifica el programa perquè llegeixi el text obert o xifrat d'un fitxer i escrigui el resultat a un altre fitxer.

### Tracta files incompletes

Modifica el programa perquè, si l'última fila és més curta que `k`, encara xifiqui i desxifri correctament, tractant els caràcters que faltin o afegint ompliment.

