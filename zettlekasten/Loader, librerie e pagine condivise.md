[[Memoria nei sistemi operativi]]
## Loader
questa è una componente del kernel che va creare un processo.
- verifica permessi
- copia il codice 
- carica librerie condivise 
- avviare il main 

abbiamo quindi una vita di un [[Processi e thread]]. Il loader si dedica anche a caricare delle librerie condivise.
## Librerie e pagine condivise
le librerie sono dei file che hanno codice eseguibile. Non hanno main, semplicemente ci si ritrova un insieme di funzioni che sono utilizzabili.

il loader si dedica a inserire e scegliere le librerie da inserire. Questi sono nel file ELF creato dalla presenza del codice. 

tutte queste zone di memoria condivisa sono contenute in mezzo al heap e allo stack, come nel [[Layout della memoria]] ricordando il concetto di [[Memoria virtuale]]

### Correlati 
- [[Gestione della memoria in bash]] 

