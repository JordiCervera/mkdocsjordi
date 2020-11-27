# Entorn de desenvolupament Servidor
Benvinguts al mòdul de d'Entorn de Desenvolupament orientat a Servidor!


# 
El model
El model representa la part de l'aplicació que implementa la lògica de negoci. Aixó significa que és responsable de la recuperació de dades convertint-los en conceptes significatius per a l'aplicació, així com el seu processament, validació, associació i qualsevol altra tasca relativa a la manipulació d'aquestes dades.

A primera vista els objectes del model poden ser considerats com la primera capa de la interacció amb qualsevol base de dades que podria estar utilitzant la teva aplicació. Però en general representen els principals conceptes entorn dels quals es desitja implementar un programa.

En el cas d'una xarxa social, la capa de model es faria càrrec de tasques tals com guardar dades de l'usuari, l'emmagatzemament d'associacions amb amics, l'emmagatzematge i la recuperació de fotos dels usuaris, trobar suggeriments de nous amics, etc. Mentre que els objectes del model poden ser considerats com a “Amic”, “Usuari”, “Comentari” i “Foto”.

El model és el responsable de:

Accedir a la capa d'emmagatzematge de dades. L'ideal és que el model sigui independent del sistema d'emmagatzematge.
Defineix les regles de negoci (la funcionalitat del sistema). Un exemple de regla pot ser: "Si la mercaderia demanada no està en el magatzem, consultar el temps de lliurament estàndard del proveïdor".
Notificarà a les vistes, si cal, els canvis que en les dades pugui produir un agent extern (per exemple, un fitxer per lots que actualitza les dades, un temporitzador que desencadena una inserció, etc.).

# El controlador
La capa del controlador gestiona les peticions dels usuaris. És responsable de respondre la informació sol·licitada amb l'ajuda tant del model com de la vista.

Els controladors poden ser vists com a administradors cuidant que tots els recursos necessaris per completar una tasca es deleguin als treballadors més adequats. Espera peticions dels clients, comprova la seva validesa d'acord a les normes d'autenticació o autorització, delega la cerca de dades al model i selecciona el tipus de resposta més adequat segons les preferències del client. Finalment delega aquest procés de presentació a la capa de la Vista.

El controlador és responsable de:

Rebre els esdeveniments d'entrada (un clic, un canvi en un camp de text, etc.).
Conté regles de gestió d'esdeveniments, del tipus "SI Esdeveniment Z, llavors Acció W". Aquestes accions poden suposar peticions al model o a les vistes. Una d'aquestes peticions a les vistes pot ser una trucada al mètode "Actualitzar()". Una petició al model pot ser "Obtenir_temps_de_lliurament ( nova_ordre_de_venda )".

# La vista
La vista fa una presentació de les dades del model separada dels objectes del model. És responsable de l'ús de la informació de la qual disposa per produir qualsevol interfície de presentació de qualsevol petició que es present.

Per exemple, com la capa de model retorna un conjunt de dades, la vista els usaria per fer una pàgina HTML que els contingui. O un resultat amb format XML perquè altres aplicacions puguin consumir.

La capa de la Vista no es limita únicament a HTML o text que representi les dades, sinó que pot ser utilitzada per oferir una àmplia varietat de formats en funció de les seves necessitats tals com videos, música, documents i qualsevol altre format que puguis imaginar.

Les vistes són responsables de:

Rebre dades del model i els mostra a l'usuari.
Tenen un registre del seu controlador associat (normalment perquè a més ho instància).
Poden donar el servei de "Actualització()", perquè sigui invocat pel controlador o pel model (quan és un model actiu que informa dels canvis en les dades produïdes per altres agents).


<img src="/img/institut.jpg"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />