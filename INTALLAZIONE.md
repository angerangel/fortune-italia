# Installazione

NOTA CONSOLATORIA: La lunghezza di un file di INSTALLAZIONE e' inversamente proporzionale alla difficolta' dell'installazione medesima.

NOTA DI PREAMBOLO: Prima di procedere, leggere il file COPYING.

NOTA MORALE: L'installazione del file "zozzital" (che NON E' CODIFICATO in alcun modo (ROT-13), e quindi risulta immediatamente leggibile) comporta successivamente la visualizzazione di messaggi contenenti parolacce, frasi o situazioni "sporche" o considerate potenzialmente o effettivamente immorali od offensive, anche a sfondo sessuale o razzista. Installate tale file SOLAMENTE se voi (ed i vostri utenti) siete sicuri di essere TOTALMENTE immuni da qualunque tipo di offesa verbale. In caso contrario, EVITATE l'installazione di "zozzital", semplicemente non eseguendo le operazioni descritte piu' sotto e relative a tale file.

NOTA IMPORTANTE: Per l'installazione convenzionale dei fortune bisogna essere loggati come root. Vedi punto 2 per l'installazione per un singolo utente.

NOTA SUGLI AGGIORNAMENTI: Se state aggiornando una precedente installazione di fortune.it, continuano a valere le operazioni cosi' come sono di seguito descritte: i vecchi file "italia" e "zozzital", con i rispettivi ".dat", saranno sovrascritti, com'e' corretto che avvenga. Per semplicita' di gestione, non sono previste patch ".diff" pubbliche.

NOTA SULLE DISTRIBUZIONI DI LINUX: Le procedure di installazione qui riportate si riferiscono ad un sistema Linux derivante da una distribuzione Slackware, in cui i file di fortune sono contenuti nella directory "/usr/share/games/fortunes". Non e' cosi' in tutte le distribuzioni (provate "man fortune", se lo avete). In particolare, circa la Slackware, devono essere stati precedentemente installati i dischi della serie "Y" ("Games"), con cui viene installato anche il package dei fortune in inglese (se questo e' troppo semplice, per voi, potete sempre rintracciare i sorgenti dei comandi "fortune" e "strfile" e compilarveli, evitando in tal modo l'installazione dei fortune in inglese...).

NOTA EXTRA-LINUX: A patto che abbiate un programma "fortune" analogo a quello in Linux (sono reperibili i sorgenti), i fortune.it possono essere installati ovunque, sia sui vari Unix che su MS-DOS/Windows, Amiga, Macintosh, OS/2, MSX, VIC20, ecc. (nessun porting e' previsto per le centraline d'iniezione elettroniche fabbricate prima del 1996...). :) NOTA DI (IN)COMPATIBILITA' CON MICRO$OFT WINDOW$: Qualsiasi installazione si scelga, non serve fare il reboot della macchina. :-)

NOTA FUTILE: Se vi rimane tempo, e se siete collegati ad Internet, segnalatemi in mailbox (a maxint@tiscali.it, vedi sotto la sintassi preferita) che avete installato i fortune in italiano. Cio' non vuole assolutamente comportare alcun tipo di monitoraggio spionistico stile "Grande Fratello", ne' puo' in alcun modo compromettere la sicurezza del vostro sistema. Serve solamente come "incoraggiamento morale" a proseguire: se vediamo che molta gente usa i nostri fortune, sara' piu' facile e gratificante continuare ad aggiornare questo package... :-)
1 - INSTALLAZIONE CONVENZIONALE, COME root:

Andare nella directory fortune, e creare una cartella dove riporre quelli in inglese (possono sempre tornare utili con qualche amico/a straniero/a) e create una sottocartella ancora fortunes: (diventate root)

 cd /usr/share/games/fortunes
 mkdir inglesi
 mv * inglesi/
 mkdir fortunes

Ora copiate i file "italia" e "zozzital" (tralasciare quest'ultimo, se lo si reputa troppo "sporco" o volgare) nella directory "/usr/share/games/fortunes/fortunes/" (o nell'equivalente della vostra distribuzione, ad esempio "/var/lib/games/fortunes" o "/var/lib/fortunes": se non la trovate, possono esservi d'aiuto i comandi "which fortune", "whereis fortunes" oppure "locate fortune"):
sempre come root)

 cp italia animali zozzital /usr/share/games/fortunes/fortunes

Generare i file ".dat" che indicizzano i fortune:

 cd /usr/share/games/fortunes/fortunes (o directory equivalente)
 strfile italia
 strfile zozzital
 strfile animali

Ora lanciate il comando "fortune" e vedete se e' andato tutto a posto:

 fortune
 Io sono il migliore che abbia mai avuto.
 -- Woody Allen

Se volete una frase inglese basta digitare "fortune inglesi" (vi ricordate la cartella creata precedentemente?):

 fortune inglesi
 Cheer Up! Things are getting worse at a slower rate.

Finito!

Spedire una mail a maxint@tiscali.it, con: "Subject: INSTALLATO fortune.it" e body vuoto, per segnalare l'avvenuta installazione; e/o: "Subject: AGGIORNAMENTI fortune.it" e body vuoto, per ricevere in mailbox un avviso di disponibilita' di nuove release.
2 - INSTALLAZIONE "NON CONVENZIONALE" PER SINGOLO UTENTE:

Se non si ha accesso come root, e la propria eventuale quota utente lo permette, si puo' ugualmente installare fortune.it. Copiare i file "italia" e "zozzital" (al solito, tralasciare quest'ultimo, se lo si reputa troppo "sporco") in una propria sottodirectory (che io chiamerei "~/.fortunes"):

 mkdir ~/sub_dir
 cp italia zozzital ~/sub_dir

Generare i file ".dat" che indicizzano i fortune:

 cd ~/sub_dir
 strfile italia
 strfile zozzital

Aggiungere il comando

 fortune ~/sub_dir/italia ~/sub_dir/zozzital

al proprio file "~/.bash_profile" (se si usa la "bash" come shell di login) od a "~/.login" (se si usa la "csh", "tcsh" o derivate come shell di login), avendo cura di eliminare dai suddetti file la precedente chiamata "fortune". Se il file di inizializzazione corrispondente alla vostra shell di login non esiste, andra` creato, copiandolo da quello di sistema comune per tutti gli utenti, eseguito di default ("/etc/profile" o "/etc/login" rispettivamente). (Se utilizzate una shell di login qui non menzionata, fate riferimento al suo manuale "man nome_shell" oppure "info nome_shell" per sapere i(l) file di inizializzazione.)

Finito! Rimuovere fortune.it-1.52.tar.gz e la directory fortune.it-1.52 . 
