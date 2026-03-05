Tenendo conto che gli INT non sono illimitati ma hanno un numero massimo di 2 milioni abbiamo cambiato il tutto usando UUID che è composto da 5 gruppi esadecimali. In media ha una composizione da 8-4-4-4-12 numeri ognuno. 

Questo non è incrementale, anche se dipendono dall'algoritmo. La generazione di questi sono quasi del tutto impossibili da generare nello stesso modo. Rende quindi quasi impossibile [[vulnerabilità ID KEY tabelle]]. 

Ci sono varie versioni: 
- UUID Temporale
	- Questo è basato su data, ora, [[MAC Address]], ecc...
	- ma questo può esporre questi dati ad altre persone.
- UUID V4
	- Questo è quasi del tutto casuale 
Link: 
- [[Chiavi nei database]]
- [[Query uso tabelle]] 
