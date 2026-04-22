# Una molt breu introducció a la criptografia

Des de l'antiguitat, quan les persones van començar a escriure, ha existit la necessitat de mantenir
algun text escrit en secret. En idear tècniques per ocultar la informació registrada,
va sorgir un nou camp científic – la criptografia.

> **La criptografia** és una disciplina científica que s'ocupa del desenvolupament
> de sistemes per xifrar informació. La paraula criptografia prové de les
> paraules gregues kryptós (*ocult, secret*) i graphein (*escriure*).

A l'Índia, escrits de 2000 anys enrere parlen de dos tipus de xifratge – el primer
tipus es basava en la substitució de lletres basada en les seves relacions fonètiques,
i el segon en un alfabet codificat aparellant lletres i utilitzant
lletres recíproques. A Pèrsia, l'actual Iran, també hi havia dos tipus de
xifratge – el primer escrit reial s'utilitzava per a la correspondència oficial dins
del regne, i el segon per a la comunicació amb altres estats.

El primer llibre sobre criptografia, titulat "El llibre dels missatges criptogràfics"
segóns les fonts històriques, va ser escrit pel filòsof àrab Al-Khalil
(717–786), en el qual es fan servir permutacions i combinacions per primera vegada
per llistar totes les paraules àrabs amb i sense vocals. No obstant això, els mètodes
de xifratge clàssics sovint revelen patrons estadístics sobre el missatge original, que poden
ser explotats per trencar el xifratge.

![Manuscrit de Kindi sobre el desxifratge de missatges criptogràfics](./images/kindi.jpg)

Després del descobriment de l'anàlisi de freqüència de lletres en un missatge, el
matemàtic àrab Al-Kindi va escriure el llibre "Manuscrit per al desxifratge de
missatges criptogràfics" al segle IX, en el qual es va descriure per primera vegada
l'ús de tècniques d'anàlisi de freqüència.

> **La criptoanàlisi** és la disciplina científica que estudia els mètodes per
> "trencar" els sistemes criptogràfics. La paraula criptoanàlisi prové de les paraules
> gregues kryptós (*ocult, secret*) i analýein (*anàlisi*).

El primer tractat conegut sobre criptografia va ser escrit en 25 pàgines per l'arquitecte
italià Leone Battista Alberti el 1467. És també el creador del cercle de xifrat
i d'altres solucions per a l'ocultació de text de doble capa. Mig segle
més tard, es va publicar l'obra de Johannes Trithemus sobre criptografia en cinc volums.
Al segle XVI, contribucions significatives van ser fetes pel metge milà
Girolamo Cardano, el matemàtic Battista Porta, i el diplomàtic francès
Blaise de Vigenere.

![Màquina de xifrat francesa en forma de llibre del segle XVI](./images/cyphermachine.jpg)

Al segle XIX, es va concloure que la criptografia no hauria de depèndre del secret
dels algoritmes de xifratge, sinó del secret de la clau. El
secret de la clau en si mateix ha de ser suficient per evitar que el missatge xifrat
sigui trencat. Això es va convertir en un dels principis fonamentals de la
criptografia, escrit el 1883 per Auguste Kerckhoffs (Principi de Kerckhoffs).
Més explícitament, va ser reiterat per Claude Shannon, el fundador
de la Teoria de la Informació i una figura clau en la criptografia teòrica, com
la Màxima de Shannon: "l'enemic coneix el sistema".

Durant la Segona Guerra Mundial, els alemanys van construir una màquina anomenada Enigma que
xifrava missatges d'una manera mai vista abans. No obstant això, per molt revolucionària
que fos en aquell moment, els Aliats, liderats per Alan Turing, van poder trencar el
sistema criptogràfic Enigma mitjançant la criptoanàlisi.

![Enigma](./images/enigma.jpg)

La criptografia i la criptoanàlisi són les dues disciplines principals de la criptologia.

> **La criptologia** és la ciència que s'ocupa de diversos aspectes de la seguretat
> de la informació. La paraula criptologia prové de les paraules gregues kryptós (*ocult,
> secret*) i logos (*ciència*).

## Present

Després de la Segona Guerra Mundial, amb el desenvolupament de la tecnologia de la informació, la criptologia
i les seves disciplines científiques van adquirir una importància creixent. Els ordinadors moderns
poden trencar xifrats simples a velocitats increïbles, de manera que els algoritmes criptogràfics s'han
tornat molt més avançats. Avui, la criptografia es divideix generalment en
xifratge **simètric**, on s'utilitza la mateixa clau tant per al xifratge com per al
desxifratge...

![Xifratge simètric](./images/symmetric.png)

...i xifratge **asimètric**, on s'utilitza un parell de claus pública i privada:

![Xifratge asimètric](./images/asymmetric.png)

Una altra eina essencial és la funció de hash criptogràfic, que crea una
empremta digital única de les dades i s'és àmpliament utilitzada en la protecció de contrasenyes,
les signatures digitals i la tecnologia blockchain.

## El futur

De cara al futur, s'espera que la criptografia quàntica es converteixi en un fonament de
la comunicació segura. Es basa en el principi d'incertesa de Heisenberg de
la física quàntica. No obstant això, la computació quàntica també representa una amenaça per a molts
algoritmes criptogràfics en ús avui, cosa que ha portat al desenvolupament de la
criptografia post-quàntica.

![Google Quantum AI](./images/google.jpg)

La importància de la criptologia en la societat moderna no es pot subestimar.
Els sistemes criptogràfics garanteixen la privacitat de les comunicacions electròniques,
permeten el comerç electrònic segur, protegeixen les criptomonedes, i en alguns països
fins i tot salvaguarden el vot electrònic i el recompte de vots.
