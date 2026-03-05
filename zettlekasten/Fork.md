[[Creazione processi]]
la fork non riceve argomenti e crea la copia del padre, un clone.
la memoria e stato sono gli stessi, hanno tutto in comune e dopo di quello andiamo a cambiare con le prossime fasi.

Il ritorno della fork (che è l'unica differenza tra padre e figlio) dipende:
- il PID del figlio se padre 
- 0 se figlio 

Fork è molta complessa ed è facile fare errori. Possiamo infatti:
- [[Fork bomb]] 
	- questo è utilizzato per spaccare computer e piantare la macchina anche a distanza dato che eseguibile sempre
	- fork in while infinito 
- difficolta di comprensione 
	- I fork devono essere compresi come ad albero e bisogna sempre tenere conto di padri e figli. 
-  ricorda che abbiamo i [[Bufferizzazione]] e tieni sempre conto di questo altrimenti non vai a capire come funzione 