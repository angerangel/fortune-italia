# Installazione

**NOTA CONSOLATORIA:** La lunghezza di un file di INSTALLAZIONE e' inversamente proporzionale alla difficolta' dell'installazione medesima.

**NOTA DI PREAMBOLO:** Prima di procedere, leggere il file COPYING.

**NOTA MORALE:** L'installazione del file "zozzital" (che NON E' CODIFICATO in alcun modo (ROT-13), e quindi risulta immediatamente leggibile) comporta successivamente la visualizzazione di messaggi contenenti parolacce, frasi o situazioni "sporche" o considerate potenzialmente o effettivamente immorali od offensive, anche a sfondo sessuale o razzista. Installate tale file SOLAMENTE se voi (ed i vostri utenti) siete sicuri di essere TOTALMENTE immuni da qualunque tipo di offesa verbale. In caso contrario, EVITATE l'installazione di "zozzital", semplicemente non eseguendo le operazioni descritte piu' sotto e relative a tale file.

**NOTA IMPORTANTE:** Per l'installazione convenzionale dei fortune bisogna essere loggati come root. Vedi punto 2 per l'installazione per un singolo utente.

**NOTA SUGLI AGGIORNAMENTI:** Se state aggiornando una precedente installazione di fortune.it, continuano a valere le operazioni cosi' come sono di seguito descritte: i vecchi file "italia" e "zozzital", con i rispettivi ".dat", saranno sovrascritti, com'e' corretto che avvenga. Per semplicita' di gestione, non sono previste patch ".diff" pubbliche.

**NOTA SULLE DISTRIBUZIONI DI LINUX:** Le procedure di installazione qui riportate si riferiscono ad un sistema Linux tipico, in cui i file di fortune sono contenuti nella directory "/usr/share/games/fortunes". Non e' cosi' in tutte le distribuzioni (provate "man fortune", se lo avete). In particolare, circa la Slackware, devono essere stati precedentemente installati i dischi della serie "Y" ("Games"), con cui viene installato anche il package dei fortune in inglese (se questo e' troppo semplice, per voi, potete sempre rintracciare i sorgenti dei comandi "fortune" e "strfile" e compilarveli, evitando in tal modo l'installazione dei fortune in inglese...).

**NOTA EXTRA-LINUX:** A patto che abbiate un programma "fortune" analogo a quello in Linux (sono reperibili i sorgenti), i fortune.it possono essere installati ovunque, sia sui vari Unix che su MS-DOS/Windows, Amiga, Macintosh, OS/2, MSX, VIC20, ecc. (nessun porting e' previsto per le centraline d'iniezione elettroniche fabbricate prima del 1996...). :) NOTA DI (IN)COMPATIBILITA' CON MICRO$OFT WINDOW$: Qualsiasi installazione si scelga, non serve fare il reboot della macchina. :-)


## 1 - INSTALLAZIONE CONVENZIONALE, COME root:

Se usate Ubuntu o simili, prima di tutto lanciate:

    sudo apt-get install fortune

Andare nella directory fortune, e creare una cartella dove riporre quelli in inglese (possono sempre tornare utili con qualche amico/a straniero/a) e create una sottocartella ancora fortunes: (diventate root)

    cd /usr/share/games/fortunes
    mkdir inglesi
    mv * inglesi/

Ora copiate i file dentro "testi", come "italia" e "zuse-o" (tralasciare quelli che finiscono con -o, perchè sono un po' piu' "sporchi" o volgari) nella directory "/usr/share/games/fortunes/fortunes/" (o nell'equivalente della vostra distribuzione, ad esempio "/var/lib/games/fortunes" o "/var/lib/fortunes": se non la trovate, possono esservi d'aiuto i comandi "which fortune", "whereis fortunes" oppure "locate fortune") sempre come root:

    cd testi
    cp * /usr/share/games/fortunes/

Generare i file ".dat" che indicizzano i fortune:

    cd /usr/share/games/fortunes/   # (o directory equivalente)
    for i in * ; do strfile "$i"  ; done
    
(su ubuntu:  `for i in * ; do sudo strfile "$i"  ; done`)

Ora lanciate il comando "fortune" e vedete se e' andato tutto a posto:

    fortune
    
    Io sono il migliore che abbia mai avuto.
    -- Woody Allen

Se volete una frase inglese basta digitare "fortune inglesi" (vi ricordate la cartella creata precedentemente?):

    fortune inglesi
    
    Cheer Up! Things are getting worse at a slower rate.

Finito!

## 2 - INSTALLAZIONE "NON CONVENZIONALE" PER SINGOLO UTENTE:

Se non si ha accesso come root, e la propria eventuale quota utente lo permette, si puo' ugualmente installare fortune.it. Copiare i file "italia" e "zozzital" (al solito, tralasciare quest'ultimo, se lo si reputa troppo "sporco") in una propria sottodirectory (che io chiamerei "~/.fortunes"):

    cd testi
    mkdir ~/sub_dir
    cp *  ~/sub_dir

Generare i file ".dat" che indicizzano i fortune:

    cd ~/sub_dir
    for i in * ; do strfile "$i"  ; done

Aggiungere il comando

    fortune ~/sub_dir/italia 

al proprio file "\~/.bash_profile" o "\~/.bashrc" (se si usa la "bash" come shell di login) od a "\~/.login" (se si usa la "csh", "tcsh" o derivate come shell di login),
avendo cura di eliminare dai suddetti file la precedente chiamata "fortune".
Se il file di inizializzazione corrispondente alla vostra shell di login non esiste, 
andra' creato, copiandolo da quello di sistema comune per tutti gli utenti, eseguito di default ("/etc/profile" o "/etc/login" rispettivamente). 
(Se utilizzate una shell di login qui non menzionata, fate riferimento al suo manuale "man nome_shell" oppure "info nome_shell" per sapere i(l) file di inizializzazione.)

Finito! Rimuovere fortune.it-xxx.tar.gz e la directory fortune.it-xxx . 
