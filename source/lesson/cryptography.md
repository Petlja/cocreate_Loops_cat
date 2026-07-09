# Una Breu Introducció a la Criptografia

Desde l'antiguitat, quan les persones van començar a escriure, ha existit la necessitat de mantenir
alguns textos escrits en secret. Al desenvolupar tècniques per amagar informació registrada,
va sorgir un nou camp científic – la criptografia.

> **La criptografia** és una disciplina científica que s'ocupa del desenvolupament
> de sistemes per xifrar informació. La paraula criptografia prové de les
> paraules gregues kryptós (*ocult, secret*) i graphein (*escriure*).

A l'Índia, escrits de fa 2000 anys parlen de dos tipus de xifratge – el primer
tipus es basava en la substitució de lletres segons les seves relacions fonètiques,
i el segon en un alfabet codificat mitjançant l'emparellament de lletres i l'ús
de lletres recíproques. A Pèrsia, el atual Iran, també hi havia dos tipus de
xifratge – el primer guió real s'usava per a la correspondència oficial dins
del regne, i el segon per a la comunicació amb altres estats.

El primer llibre sobre criptografia, titulat "El Llibre dels Missatges Criptogràfics"
segons fonts històriques, va ser escrit pel filòsof àrab Al-Khalil
(717–786), en el qual s'utilitzen per primera vegada permutacions i combinacions
per enumerar totes les paraules àrabs amb i sense vocals. Tanmateix, els mètodes de xifratge
clàssics sovint revelen patrons estadístics sobre el missatge original, que poden
aprofitar-se per desxifrar el codi.

![Manuscrit de Kindi sobre el desxiframent de missatges criptogràfics](./images/kindi.jpg)

Tras el descobriment de l'anàlisi de freqüència de lletres en un missatge, el
matemàtic àrab Al-Kindi va escriure el llibre "Manuscrit per al Desxiframent de
Missatges Criptogràfics" al segle IX, en el qual es va descriure per primera vegada
l'ús de tècniques d'anàlisi de freqüència.

> **El criptoanàlisi** és la disciplina científica que estudia mètodes per
> "trencar" sistemes criptogràfics. La paraula criptoanàlisi prové de les paraules
> gregues kryptós (*ocult, secret*) i analýein (*anàlisi*).

El primer tractat conegut sobre criptografia va ser escrit en 25 pàgines per l'arquitecte italià
Leone Battista Alberti el 1467. Ell és també el creador del cercle xifrador
i altres solucions per a l'ocultament de text en doble capa. Mig segle
despres, va ser publicada l'obra de Johannes Trithemus sobre criptografia en cinc volums.
Al segle XVI, van realitzar aportacions significatives el metge milanès
Girolamo Cardano, el matemàtic Battista Porta i el diplomàtic francés
Blaise de Vigenere.

![Màquina Xifrada Francesa en Forma de Llibre del Segle XVI](./images/cyphermachine.jpg)

Al segle XIX, es va arribar a la conclusió que la criptografia no havia de basar-se en el
secreto dels algoritmes de xifratge, sinó en el secret de la clau. El
secreto de la pròpia clau ha de ser suficient per evitar que el missatge xifratge
sigui desxifrat. Això es va convertir en un dels principis fonamentals de
la criptografia, escrit el 1883 per Auguste Kerckhoffs (Principi de Kerckhoffs).
De forma més explícita, va ser reiterat per Claude Shannon, el fundador
de la Teoria de la Informació i figura clau en la criptografia teòrica, com
la Màxima de Shannon: "l'enemic coneix el sistema".

Durant la Segona Guerra Mundial, els alemanys van construir una màquina anomenada Enigma que
xifrava missatges d'una forma mai vista abans. Tanmateix, per revolucionària que
fos en el seu moment, els Aliats, liderats per Alan Turing, van ser capaços de desxifrar el
sistema criptogràfic Enigma mitjançant el criptoanàlisi.

![Enigma](./images/enigma.jpg)

La criptografia i el criptoanàlisi són les dues disciplines principals de la criptologia.

> **La criptologia** és la ciència que s'ocupa dels distints aspectes de la seguretat
> de la informació. La paraula criptologia prové de les paraules gregues kryptós (*ocult,
> secret*) i logos (*ciència*).

## Present

Tras la Segona Guerra Mundial, amb el desenvolupament de la tecnologia de la informació, la criptologia
i les seves disciplines científiques es van tornar cada vegada més importants. Els ordinadors moderns
poden desxifrar codis simples a velocitats incredibles, per la qual cosa els algoritmes criptogràfics s'han
tornat molt més avançats. Avui en dia, la criptografia es divideix generalment en
xifratge **simètric**, on s'usa la mateixa clau tant per xifrar com per
desxifrar...

![Xifratge simètric](./images/symmetric.png)

...i xifratge **asimètric**, on s'utilitza un parell de claus pública i privada:

![Xifratge asimètric](./images/asymmetric.png)

Una altra eina essencial és la funció hash criptogràfica, que crea una
huella digital única de les dades i s'usa àmpliament en la protecció de contrasenyes,
firmes digitals i tecnologia blockchain.

## El Futur

Mirant cap al futur, s'espera que la criptografia quàntica es converteixi en un pilar de
la comunicació segura. Es basa en el principi d'incertesa de Heisenberg de
la física quàntica. Tanmateix, la computació quàntica també representa una amenaça per a molts
algorimes criptogràfics en ús avui en dia, la qual cosa ha portat al desenvolupament de
la criptografia postquàntica.

![Google Quantum AI](./images/google.jpg)

La importància de la criptologia en la societat moderna no pot subestimar-se.
Els sistemes criptogràfics garanteixen la privacitat de les comunicacions electròniques,
habiliten el comerç electrònic segur, protegeixen les criptodivisas i en alguns països
inclús salvaguarden la votació electrònica i el recompte de vots.
Tanmateix, també sorgeixen nombroses qüestions ètiques. ¡Prepara't per a un debat!

## Debat

**Tema del debat: ¿Hauria el dret a la privacitat ser més important que la seguretat de la societat?**

Divisió de rols

Equip A – A favor de la forta protecció de la privacitat

Cada persona té dret a la comunicació privada.
El xifratge protegeix els ciutadans de l'abús, el robatori d'identitat i la vigilància.
Nadie, ni tan sols l'estat, hauria de tenir accés als missatges privats sense una base legal clara.

Equip B – A favor de més supervisió per a la seguretat

El xifratge complet pot ajudar els criminals i terroristes a amagar les seves activitats.
Els serveis de seguretat a vegades necessiten accés a les comunicacions per protegir els ciutadans.
La societat ha de trobar un equilibri entre privacitat i seguretat.

Pots dur a terme la consideració d'arguments en grups entre dues classes o durant la classe, seguit per un intercanvi de punts de vista (cada equip té 5 minuts per presentar la seva posició). Altres estudiants – el jurat – després fan preguntes i ambdós equips tienen aproximadament 10 minuts per respondre.

L'avaluació i determinació de l'equip guanyador no és necessària, però es recomana una discussió conjunta sobre totes les conclusions presentades.

## Preguntes per a la reflexió

¿Hauria la policia de tenir dret d'accedir als missatges xifratges dels sospitosos?
¿Estaries d'acord que s'analitzin els teus missatges si això evités un atac terrorista?
¿Quins són els riscos si algú té accés a totes les nostres dades?
¿Són les xarxes socials prou transparents sobre les dades que recopilen?
¿Són conscients els joves de quants dades personals deixen a Internet?
¿Es suficient una contrasenya per protegir un compte o es necessiten mesures de seguretat addicionals?