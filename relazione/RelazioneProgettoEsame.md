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

aggiungere *flusso di gestione documentale*

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
[1]Esso è stato creato dall'International Digital Publishing Forum (IDPF), un consorzio di aziende che comprende editori, distributori e sviluppatori di lettori che si occupano di mantenerlo aggiornato, 
nel 2007 ed è considerato dal W3C il principale standard pubblico per la creazione di libri digitali in contrapposizione 
a quelli proprietari come Mobipocket o AZW di Amazon. È stato scelto un nome generico come "Electronic Publication"
per indicare il fatto che tale formato può essere utilizzato per la creazione di un qualsiasi documento, 
come libri, riviste, giornali purchè essi siano distribuibili in formato digitale. ePub è un formato
che si basa su XML ed è da considerarsi, per certi versi, una versione aggiornata e sostitutiva dell'*Open eBook* (OeBPS).
L'estensione del file è .epub e la sua caratteristica principale, essendo un formato di testo, è quella di essere "reflowable" il che 
significa che il contenuto può adattarsi dinamicamente alle dimensioni dello schermo del dispositivo di visualizzazione.
Il formato è costituito da tre specifiche: l'*Open Publication Structure* (OPS), che decsrive come marcare i contenuti del file, 
l'*Open Packaging Format* (OPF), che descrive in XML la struttura del file .epub, e l'*OEBPS Container Format* (OCF), che descrive 
il metodo per costruire l'archivio ZIP che conterrà la pubblicazione. Andando ad aprire l'archivio .epub realizzato 
per questo progetto si può riscontrare la seguente struttura: il file *mimetype* con la dichiarazione del formato (*application/epub+zip*), 
la cartella *META-INF* contenente il file *container.xml*, il quale contiene il file principale dell'applicazione, il file 
root che il reader dovrà leggere per sapere come organizzare il documento e infine la cartella *EPUB*, che ha sostitui la directory OEBPS
in EPUB3, che contiene il file *content.opf*, il file *toc.ncx* e le cartelle *images*, *styles* e *text*
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
> **pandoc project.html --css=stylesheet.css --epub-cover-image=cover.jpg --epub-metadata=metadata.xml  --toc -o L'IA_nel_processo_editoriale.epub**  
Tale comando consente anche di associare al documento ePub un foglio di stile CSS, una copertina contenuta nel file cover.jpg,
un file contenenti i metadati del libro (metadata.xml) e di includere un sommario che verrà generato in automatico.

## Ideazione

### Tema

In questa fase iniziale, ma fondamentale per la creazione dell'opera, si è individuato il tema e si è definito il concetto principale
della pubblicazione, quindi in questo caso l'argomento principale di un'opera che può essere collegata alla didattica. 
Sono state fatte ricerche e analisi delle tendenze attuali nel settore editoriale ed è stato individuato il target dell'opera, ovvero
i ![destinatari](#destinatari) che verranno descritti qui sotto. Si sono raccolte informazioni relative al tema 
dell'intelligenza artificiale nel processo editoriale, impiegando anche strumenti e operatori di ricerca avanzata come quelli di Google.

### Destinatari
Descrivere i destinatari del prodotto editoriale descrivendo le personas alle quali si rivolge il prodotto. Descrivete alcuni scenari d'uso nei quali inserire le personas scelte come destinatari.

> LM2 slide 29-32

### Requisiti di accettazione
Indicate i requisiti di accettazione che dovranno essere soddisfatti per raggiungere i destinatari. Quali modelli di fruizione consideriamo più efficaci per i nostri destinatari? Quali standard consideriamo come riferimento? Quali aspetti di innovazione possiamo proporre? Nella qualità dei contenuti o nel processo di fruizione?

> LM4

### Canali di distribuzione
Presentare i canali di distribuzione che si intendono raggiugnere e i formati dati richiesti da ogni canale. Esempi di canali sono: (i) Web, (ii) Social, (iii) Market place, (iv) Intranet. Esempi di formati. (i) Word, (ii) ePub, (iii) CBZ, (iv) PDF, (v) WebBook. 
Proporre alcuni accenni relativi all'identità visuale e alle regole tipografiche o di stile che si intendono seguire. Nel settore esisto classi di documento standard? Dati gli obiettivi è importante trasmettere un senso di adesione a modelli già conosciuti o un senso di innovazione? Lo stile sarà orientato verso un'espressione formale o informale?

## Processo di Produzione

### Acquisizione dei contenuti
Descrivere le fonti che saranno utilizzate nella costruzione del prodotto editoriale. Nella scelta delle fonti valutare il costo di acquisizione: (i) disponibili come fonti libere, (ii) generabili automaticamente, (iii) richiedono un lavoro di redazione manuale.

### Gestione documentale

Descrivere il *flusso di gestione documentale* definito per il progetto. Ad esempio, (i) la raccolta o produzione dei contenuti, (ii) la valutazione dei diritti, (iii) la trasformazione dei formati, (iv) la strutturazione dei contenuti, (v) l'applicazione dello stile grafico, (vi) la generazione dei metadati, (vii) la distribuzione dei contenuti. Nella descrizione del flusso considerare le  fasi di revisione, controllo e approvazione che possono richiedere le diverse fasi.

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

Elencare i riferimenti bibliografici e risorse online che hanno maggiormente contribuito alla realizzazione del progetto. Ad esempio [@sechi2010,@pantieri2021,@ceravolo2023]
