[[Memoria nei sistemi operativi]]
## Layout della memoria
ricordiamo che un processo ha un enorme spazio di [[Memoria virtuale]]
- tipicamente un processo va ad inserire ai processi più basse
- questa convenzione è implementato dal compilatore
- in media usiamo dall'estremo alto e quello basso
	- stack: alto verso il basso, posizioniamo variabili 
	- heap: cresce dal basso verso l'alto con la malloc
- la memoria ha questa forma:
	- codice:
		- questa si trova negli indirizzi bassi
		- deve essere in memoria
		- il codice è read only
	- Dati:
		- vanno le variabili globali
		- abbiamo: 
			- globali inizializzate
			- variabili globali 
	- Heap: 
		- si espande in alto per la [[Memoria dinamica]]
	- Stack: 
		- funziona come una pila
		- funziona grazie alla malloc
		- ha due operazioni fondamentale:
			- push, inserire nella "torre"
			- pop, rimuove elemento
		- contiene le variabili locali, parametri, return index 