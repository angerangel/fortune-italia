# fortune-italia 
**In breve:** questo repository vorrebbe essere una versione sempre aggiornata dalla comunità del database ufficiale dei fortune.

## Breve storia

Tutto iniziò con i *fortune*: si tratta dell'equivalente informatico dei biscottini della fortuna (approfondimenti alla [voce "Fortune" di Wikipedia](https://en.wikipedia.org/wiki/Fortune_%28Unix%29#Purpose)).

Dal 1998 al 2004 (e sì, è passato tanto tempo) *Mirko Caserta* inizialmente e poi *Andrea 'Zuse' Balestrero* hanno manutenuto una versione italiana del database dei file *fortune*, reperibile presso [http://www.fortune-it.net/main.html](http://www.fortune-it.net/main.html) insieme a tutte le informazioni del caso.

## L'idea di questo repository
Essendomi divertito non poco con i fortune, e poi avendo scoperto quelli in italiano, mi sono rattristato non poco a vedere che il pacchetto *fortune-it* non è più aggiornato da quasi 12 anni *[dal sito fortune-it.net: «ultimo aggiornamento a queste pagine o al package fortune-it qui contenuto: venerdì 3 dicembre 2004»]*.

Quello che mi sarebbe piaciuto vedere, in quest'era in cui anche scrivere dei progetti software può diventare un'operazione sociale, è un aggiornamento costante di questo pacchetto fatto da chiunque avesse avuto il piacere di contribuire in maniera intelligente e costruttiva.

Come da indicazioni nel package originale, ho provato a contattare *Andrea Balestrero* qualche settimana fa *[28 marzo 2016]*, per capire se potevamo provare insieme a rendere sociale *fortune.it*.

Non avendo ricevuto alcuna risposta (probabilmente quell'indirizzo email è poco consultato), e non trovando nessuna informazione contraria sulla licenza d'uso, ho deciso di iniziare da solo, _volenteroso di condividere con qualcun altro questa esperienza_.

A proposito di licenza: dal file *COPYING* del package originale (che consiglio comunque di leggere): «Considerate freeware (public domain) questo package» e dal file *lsm*: «Copying-policy:	Freeware».

## Il futuro?
Per il futuro vorrei che questa mia idea portasse il pacchetto a crescere e attualizzarsi costantemente.

Mi piacerebbe anche che fungesse da "spinta" per la realizzazione di nuovi player di *fortune* per varie piattaforme, magari in grado di *autoaggiornarsi* con le versioni, sempre più recenti, dei file di database che saranno qui pubblicati.

## Come funziona? In poche parole

Fortune e' un programma che estrae una frase a caso da un file. Esempio

    fortune
      
     Dio ha creato i numeri interi; tutto il resto e' lavoro dell'Uomo. 
     - Kronecker, matematico tedesco  

Per aggiungere delle frasi, o eliminare altre, basta andare nella directory di fortune (di solito **/usr/share/fortune/** e vedere se e' presente una directory chiamata **"fortunes"**, se non c'e' createla. A questo punto spostate tutti i file di testo e .dat in quest'ultima directory appena creata.

I file di testo contengono le frasi estratte a caso dal programma, ogni frase e' separata dal simbolo %. Per aggiungere una frase basta aggiungerlo in uno dei file di testo e similmente per cancellarlo basta eliminarlo. Ogni file modificato va indicizzato per essere utilizzato, e va usato il comando strfile, esempio:

     strfile barzellette 

Si possono usare piu' file di testo, poiche' e' possibile indicare a fortune se utlizzare solo una specifica lista, inoltre e' possibile unducare con che probabilita' deve esere scelto un file tra i vari file.

     fortune 90% barzellette 10% barzellettesporche

