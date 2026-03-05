[[Sistemi operativi]]
## Definizione 
I sistemi hanno una piramide di memorie, con memoria grandi e lente fino alla cpu con registri contati. Studia la storia della [[Evoluzione memoria]] per capire al meglio come funziona il tutto. 

## Page fault 
quando la MMU quando non riesce a trovare la pagina genera un interrupt. Il SO interrompe il processo e si cerca di andare a rimpiazzare le pagine

## Rimpiazzamento delle pagine 
Vediamo gli approcci:
- FIFO (rimuovo quello più vecchio)
- rimuovere quello che non mi servirà per il prossimo futuro
	- il problema è che non si può implementare
- quello che usiamo è il last recently used
	- abbastanza furbo ma non benissimo 
- esiste anche least frequently used 
	- teoricamente meglio ma difficile da realizzare
 il program break è l'indirizzo massimo per parte bassa
### Correlati 
- [[Evoluzione memoria]] 
- [[Layout della memoria]] 
- [[Loader, librerie e pagine condivise]] 
- [[Memoria statica]] 
- [[Memoria dinamica]] 
- [[Memoria virtuale]] 