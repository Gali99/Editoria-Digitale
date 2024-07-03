---
title: Relazione del progetto d'esame di Editoria Digitale
author: Simone Galimberti 10255A
date:  a.a. 2023/2024
institute: Università degli Studi di Milano
course: Editoria Digitale
version: 0.1
kind: Document
bibliography: bibliografia.bib
csl: IEEE.csl
---

![Logo UNIMI](./logo/minerva.jpg){width=100px height=100px}

# L'IA nel processo editoriale

## Introduzione

L'obiettivo era quello di realizzare un progetto che includesse alcune delle metodologie e degli strumenti
presentati durante il corso. In questo caso specifico è stato realizzato un libro digitale (Ebook) seguendo le specifiche dello
standard ![ePub](#epub) (Electronic Publication), le cui principali specifiche sono presentate qui sotto. Il libro 
è stato dapprima redatto in HTML (HyperText Markup Language) e successivamente convertito in ePub utilizzando ![Pandoc](#pandoc), un potente strumento 
di conversione che verrà brevemente descritto sotto. Il tema centrale della pubblicazione è l'applicazione dell'intelligenza artificiale 
all'interno delle diverse fasi del processo di produzione editoriale, a partire dalla fase di acquisizione dei contenuti fino alla distribuzione del prodotto.
Come indicato anche all'interno del libro, a scopo didattico alcuni dei contenuti sono stati generati mediante proprio l'utilizzo dell'intelligenza 
artificiale al fine di verificarne l'affidabilità e la coerenza nell'automazione della scrittura dei contenuti. I contenuti sono stati controllati dall'autore e si 
sono dimostrati effettivamente coerenti con l'argomento del libro e quindi si è potuto notare, anche nella pratica, che l'intelligenza artificiale 
può essere uno strumento utile nell'automazione della produzione di semplici contenuti editoriali.

### ePub
Esso è stato creato dall'International Digital Publishing Forum (IDPF), un consorzio di aziende che comprende editori, distributori e sviluppatori di lettori che si occupano di mantenerlo aggiornato, 
nel 2007 ed è considerato dal W3C il principale standard pubblico per la creazione di libri digitali in contrapposizione 
a quelli proprietari come Mobipocket o AZW di Amazon. È stato scelto un nome generico come "Electronic Publication"
per indicare il fatto che tale formato può essere utilizzato per la creazione di un qualsiasi documento, 
come libri, riviste, giornali purchè essi siano distribuibili in formato digitale. ePub è un formato
che si basa su XML ed è da considerarsi, per certi versi, una versione aggiornata e sostitutiva dell'*Open eBook* (OeBPS).
L'estensione del file è .epub e la sua caratteristica principale, essendo un formato di testo, è quella di essere "reflowable" il che 
significa che il contenuto può adattarsi dinamicamente alle dimensioni dello schermo del dispositivo di visualizzazione.
Il formato è costituito da tre specifiche: 
* l'*Open Publication Structure* (OPS), che decsrive come marcare i contenuti del file, 
* l'*Open Packaging Format* (OPF), che descrive in XML la struttura del file .epub, 
* l'*OEBPS Container Format* (OCF), che descrive il metodo per costruire l'archivio ZIP che conterrà la pubblicazione. 

Andando ad aprire l'archivio .epub realizzato per questo progetto si può riscontrare la seguente struttura: 
* il file *mimetype* con la dichiarazione del formato (*application/epub+zip*), 
* la cartella *META-INF* contenente il file *container.xml*, il quale contiene il file principale dell'applicazione, il file 
root che il reader dovrà leggere per sapere come organizzare il documento. 
* la cartella *EPUB*, che ha sostituito la directory OEBPS in EPUB3, che contiene il file *content.opf*, il file *toc.ncx* e le cartelle *media*, *styles* e *text*
Il file content.opf è detto Package File e contiene i metadati e le informazioni strutturali e bibliografiche dell'ebook. Esso è composto da un'intestazione XML
e da quattro sezioni: la sezione **metadata**, che fornisce al reader le informazioni di descrizione del libro, la sezione **manifest**,
che indica al reader dove trovare i contenuti, la sezione **spines**, che indica al reader in che ordine deve visulizzare i file e la sezione
**guide** che indica al reader dove trovare file speciali come la copertina o l'indice.

### Pandoc

Pandoc è una libreria scritta in Haskell per la conversione di documenti da un formato di origine a formato di destinazione
È in grado di convertire numerosi formati di markup e di elaborazione testi, tra cui vari tipi di Markdown, HTML, LaTeX, ePub e Word docx.
Pandoc ha un design modulare: un insieme di reader, che analizzano un dato formato e producono una rappresentazione astratta del documento e 
un insieme di writer, che convertono questa rappresentazione astratta in un formato di destinazione. Può essere utilizzato in diversi modi come ad 
esempio attraverso l'interfaccia grafica, Python o da linea di comando. Nel caso specifico di questo progetto è stato
utilizzato da linea di comando. Viene riportato il comando utilizzato per convertire il file HTML, con il contenuto del 
libro, in ePub: 
> ```pandoc project.html --css=stylesheet.css --epub-cover-image=cover.jpg --epub-metadata=metadata.xml  --toc -o L'IA_nel_processo_editoriale.epub```
Tale comando consente anche di associare al documento ePub un foglio di stile CSS, una copertina contenuta nel file cover.jpg,
un file contenenti i metadati del libro (metadata.xml) e di includere un sommario che verrà generato in automatico.

## Ideazione

### Tema

In questa fase iniziale, ma fondamentale per la creazione dell'opera, si è individuato il tema e si è definito il concetto principale
della pubblicazione, quindi in questo caso l'argomento principale di un'opera che può essere collegata alla didattica. 
Sono state fatte ricerche e analisi delle tendenze attuali nel settore editoriale ed è stato individuato il target dell'opera, ovvero
i ![destinatari](#destinatari) che verranno descritti qui sotto. Si sono raccolte informazioni relative al tema 
dell'intelligenza artificiale nel processo editoriale, impiegando anche strumenti e operatori di ricerca avanzata come quelli di Google. Per quanto 
riguarda la gestione documentale dei contenuti dell'opera è stata utilizzata la piattforma GitHub, la quale attraverso la creazione di un 
repository apposito ha permesso di avere una migliore organizzazione del progetto; per dettagli maggiori si rimanda a una delle ![sezioni 
successive](#gestione-documentale).

### Destinatari

I destinatari di questo ebook sono principalmente studenti universitari delle facoltà di 
Comunicazione e Giornalismo, nonché professionisti che lavorano all'interno di case editrici o 
operano in maniera indipendente nel mondo della scrittura di libri, giornali o riviste. Segue ora un'analisi
più specifica del target utilizzando il metodo delle **personas**.

La descrizione dei destinatari utilizzando il metodo delle *personas* consente di identificare ancor meglio il target
della pubblicazione andando a riconoscere più nel dettaglio le diverse esigenze, esperienze, i comportamenti e obiettivi degli utenti.
Si tratta di rappresentazioni fittizie di clienti ideali basate su dati reali e ricerche di mercato e ciascuna personas viene descritta con dettagli
come nome, età, sesso, occupazione, livello di istruzione, reddito, modelli di comportamento e atteggiamenti, motivazioni e frustrazioni.

**Personas**

1. Persona 1: Stefania, 25 anni, studentessa universitaria
   * Età: 25 anni
   * Sesso: Femmina
   * Occupazione: Studentessa universitaria di Comunicazione
   * Livello di istruzione: Laurea magistrale in corso
   * Comportamenti: Utilizza laptop e smartphone per la ricerca e la scrittura di articoli. Legge blog e segue corsi online su nuove tecnologie nel giornalismo.
   * Motivazioni: Vuole imparare come l'IA può essere utilizzata nel giornalismo per migliorare la ricerca, l'analisi dei dati e la produzione di contenuti.
   * Frustrazioni: Trova complicato integrare nuove tecnologie nei suoi progetti accademici e non è sempre sicura di quali strumenti siano i migliori.
2. Persona 2: Davide, 27 anni, redattore
   * Età: 32 anni
   * Sesso: Maschio
   * Occupazione: Redattore e correttore di bozze freelance
   * Livello di Istruzione: Laurea in Comunicazione
   * Reddito: €25,000 annui
   * Comportamenti: Usa laptop e smartphone per lavorare. Cerca strumenti che possano migliorare la qualità e l'efficienza del suo lavoro.
   * Motivazioni: Vuole trovare modi per automatizzare compiti ripetitivi per dedicare più tempo alla creatività.
   * Frustrazioni: Trova difficoltà nel tenersi aggiornato con tutte le nuove tecnologie emergenti.
3. Persona 3: Paolo, 56 anni, direttore editoriale
   * Età: 56 anni
   * Sesso: Maschio
   * Occupazione: Direttore Editoriale in una casa editrice
   * Livello di Istruzione: Laurea in Letteratura
   * Reddito: €60,000 annui
   * Comportamenti: Utilizza principalmente laptop e tablet per lavoro. Legge articoli su gestione editoriale e innovazioni nel settore.
   * Motivazioni: Vuole ottimizzare i processi di produzione, ridurre i costi e migliorare la qualità dei contenuti.
   * Frustrazioni: Difficoltà nell'implementare nuove tecnologie senza interrompere i flussi di lavoro esistenti.

Una volta definite le caratteristiche di ogni personas, al fine di comprendere sempre di più la realtà d'interesse, 
è utile predisporre degli scenari d'uso in cui si immaginano delle situazioni reali in cui le personas potrebbero
utilizzare il prodotto editoriale. Ci si concentra sul descrivere il contesto in cui si trovano, perchè utilizzano il 
prodotto e come questo soddisfa le loro esigenze.

**Scenari d'uso**
* Scenario 1: Ottimizzazione del flusso di lavoro editoriale

  Paolo, come direttore editoriale, è sempre alla ricerca di modi per ottimizzare il flusso di 
  lavoro della sua casa editrice. Legge l'ebook sull'IA nel processo di produzione editoriale e 
  scopre come l'IA può automatizzare la revisione delle bozze, migliorare la gestione dei 
  contenuti e personalizzare le raccomandazioni di lettura. Implementa un sistema di IA che 
  riduce i tempi di revisione, permettendo alla sua squadra di concentrarsi su compiti
  più creativi.


* Scenario 2: Automazione delle attività ripetitive

  Davide è un redattore freelance che lavora su numerosi progetti contemporaneamente. 
  Spesso passa ore a correggere bozze e a formattare documenti. Dopo aver letto l'ebook, 
  inizia a utilizzare strumenti di IA per la correzione grammaticale e la formattazione automatica. 
  Questo gli permette di risparmiare tempo prezioso, migliorare la qualità del suo lavoro e 
  accettare più incarichi.

* Scenario 3: Apprendimento e integrazione di nuove tecnologie

  Stefania è una studentessa di giornalismo interessata a come l'IA possa rivoluzionare il settore. 
  L'ebook le offre una panoramica completa su strumenti di IA per la ricerca di informazioni, 
  l'analisi dei dati e la generazione automatica di testi. Utilizza queste conoscenze per il suo 
  progetto di tesi, sviluppando un prototipo di piattaforma di notizie che utilizza l'IA per 
  personalizzare i contenuti in base alle preferenze dei lettori.

### Requisiti di accettazione

Per raggiungere efficacemente i destinatari di questa pubblicazione si è deciso di impiegare un modello 
di fruizione multiformato e la possibilità di avere una buona compatibilità con vari dispositivi come 
e-reader, tablet e smartphone al fine di garantire una buona flessibilità di lettura. 
Per migliorare l'accettazione da parte degli utenti si è deciso di rendere disponibile l'ebook 
in due formati altamente riconosciuti e accessibili come ePub3 e PDF. 
In questo modo viene garantita un'ottima qualità ed esperienza di lettura. 

ePub fa dell'estrema flessibilità e compatibilità con il numero più ampio possibile di sistemi
di lettura i suoi punti di forza, svincolandosi al massimo dalla dipendenza da hardware e software specifici.
Esistono infatti diversi software di lettura in grado di interpretare questo formato tra cui:

* **Stanza**: un software gratuito per la lettura di pubblicazioni digitali sviluppato da Lexycle. I formati supportati sono molti:
  ePub, Amazon Kindle, Mobipocket, PDF, HTML ecc. Il software esiste in due versioni: per iPhone/iPad e Desktop (Mac e Windows).
* **FBReader**: un software gratuito, open source e multipiattaforma per la lettura dei libri digitali; è in grado di funzionare infatti sia su
  Desktop che su dispositivi mobili, in particolare su quelli con sistema operativo Android. Supporta una grande
  varietà di formati quali ePub, Palm, Mobipocket ecc.
* **Bookworm**: una piattaforma online e gratuita per gli ePub. Permette di creare la propria biblioteca
  di ePub online e di leggere libri su qualsiasi dispositivo dotato di browser web. Se si possiede un ereader 
  in grado di interpretare gli ePub, la biblioteca online può essere sincronizzata con quella del dispositivo.
* **Calibre**: software open source, multipiattaforma di gestione di ebook. Consente di creare e di leggere ebook, la
  conversione tra formati, la gestione dei metadati e l'organizzazione di collezioni e librerie. Supporta una gran 
  varietà di formati tra cui ePub e Kindle Mobi.

PDF è un formato immagine ampiamente utilizzato e supportato su molte piattaforme. È riuscito nell'obiettivo
di rendere possibile la condivisione e distribuzione dei documenti con testi e grafica formattati su piattaforme
differenti senza alterazioni nel layout originale. La quantità di software capaci di interpretarlo e manipolarlo è ampia, 
i principali sono:
* **Acrobat Reader**: software gratuito e multipiattaforma per la lettura dei PDF, si riescono a visualizzare 
  i file codificati in tale formato a prescindere dalla piattaforma hardware e software. Inoltre, esso dà anche la 
  possibilità di effettuare ricerche all'interno dei file PDF.
* **Anteprima**: applicazione preinstallata su MAC OS capace di visualizzare immagini e PDF.

Per quanto riguarda gli aspetti di innovazione all'interno dell'ebook è presente un indice, che funge da menù di navigazione, contenente dei link
ipertestuali che puntano ad ogni sezione dell'ebook arricchendo l'esperienza di lettura e rendendola più dinamica.
I lettori possono accedere ai contenuti in maniera non sequenziale, saltando direttamente a sezioni specifiche del contenuto.

### Canali di distribuzione

I canali di distribuzione che si intendono raggiungere, ognuno con i propri formati, sono i seguenti:

1. Web
   * Il sito web ufficiale di Unimi Editore ospiterà l'ebook in formato ePub e PDF per il dowload diretto. 
     Sarà poi possibile rendere disponibile anche altri formati.
2. Social Media
   * Per promuovere l'ebook attraverso piattaforme di social media come Facebook, Instagram, X e 
     LinkedIn verranno resi disponibili estratti in PDF dell'ebook e un link diretto alla versione ePub.
     Sarà poi possibile rendere disponibili anche altri formati
3. Market Place
   * L'ebook verrà distribuito su marketplace come Amazon Kindle Store, Apple Books, Google Play Books e altri, 
     utilizzando i formati ePub e PDF per garantire la compatibilità con vari dispositivi e-reader.
     Sarà poi possibile rendere disponibili anche altri formati
4. Intranet
   * Per le case editrici e le scuole o Università che desiderano distribuire l'ebook internamente,
     verranno fornite versioni in formato PDF e Word, facili da integrare nelle piattaforme intranet.

Per quanto riguarda le **regole tipografiche e di stile**: i **paragrafi** sono brevi e ben spaziati per 
migliorare la leggibilità, un uso coerente di **intestazioni** e **sottotitoli** per una chiara struttura 
gerarchica dei contenuti e lo **stile** professionale ma accessibile, bilanciando tra formale e
informale per coinvolgere sia studenti universitari che professionisti.

## Processo di Produzione

### Acquisizione dei contenuti

Descrivere le fonti che saranno utilizzate nella costruzione del prodotto editoriale. 
Nella scelta delle fonti valutare il costo di acquisizione: 
(i) disponibili come fonti libere, (ii) generabili automaticamente, 
(iii) richiedono un lavoro di redazione manuale.

### Gestione documentale

Descrivere il *flusso di gestione documentale* definito per il progetto. 
Ad esempio, (i) la raccolta o produzione dei contenuti, (ii) la valutazione dei 
diritti, (iii) la trasformazione dei formati, (iv) la strutturazione dei contenuti, 
(v) l'applicazione dello stile grafico, (vi) la generazione dei metadati, (vii) la 
distribuzione dei contenuti. Nella descrizione del flusso considerare le  fasi di
revisione, controllo e approvazione che possono richiedere le diverse fasi.



> LM2 slide 14-26

### Tecnologie adottate

Descrivere le tecnologie addottate nelle diverse fasi e discuterne il contributo in termini di raggiungimento degli obiettivi descritti negli scenari d'uso.

|                |Scenario 1                          |Scenario 2                       |
|----------------|-------------------------------|-----------------------------|
|Markdown |`'Isn't this fun?'`            |'Isn't this fun?'            |
|XSLT       |`"Isn't this fun?"`            |"Isn't this fun?"            |
|ePud         |`-- is en-dash, --- is em-dash`|-- is en-dash, --- is em-dash|

### Esecuzione del flusso
Allegare, possibilmente attraverso il riferimento ad un repository documentale, i materiali, gli script, le configurazioni, che permettono di riprodurre il flusso di produzione documentale. I contenuti non devono necessariamente essere completi, può essere sufficiente fornire un prototipo per ogni tipologia di contenuto previsto e per ogni formato di destinazione previsto.  

## Valutazione dei risultati raggiunti

### Valutazione del flusso di produzione

Per valutare il contributo proposto valutare le diverse fasi del flusso in termini di (i) riduzione dei tempi di gestione documentale, (ii) riduzione degli errori, (iii) miglioramento della qualità dei documenti, (iv) miglioramento del livello di accettazione della tecnologia, (v) raggiungimento di nuovi canali di distribuzione, (vi) soddisfacimento di nuovi scenari d'uso.
 
### Confronto con lo stato dell'arte

Può anche essere utile confrontare una versione ASIS del flusso di gestione, senza la tecnologia o le innovazioni proposte, e una TOBE che include la tecnologia e le innovazioni proposte dallo studente.

### Limiti emersi

È importante sottolineare i limiti emersi. Come l'impossibilità di accesso ad alcune tecnologie o fasi del flusso di gestione documentale, limiti nella automazione di alcune passi di trasformazione dei formati o di integrazione delle sorgenti

## Conclusioni

Discutere i risultati ottenuti, verificando se gli obiettivi definiti dai casi d'uso siano pienamente o parzialmente raggiunti. Evidenziare gli aspetti nei quali si sono raggiunti i risultati più soddisfacenti e le limitazioni emerse.

## Bibliografia e sitografia

Elencare i riferimenti bibliografici e risorse online che hanno maggiormente contribuito alla realizzazione del progetto. Ad esempio [@sechi2010,@ceravolo2023]
