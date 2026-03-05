[[Segnali in linux]]
## Signal handler 
- un signal handler è un flusso di esecuzione concorrente
- ma attenzione che questo può avere risultati inconsistenti 
	- quando agiamo in modo concorrente, dato che stiamo andando a modificare il main [[Thread]], serve per far si che il tutto funzioni in modo pulito e chiaro. Non ci devono essere errori con programmi che agiscono contemporaneamente. 
- Funzione rientrante 
	- può essere usata con sicurezza
	- le [[System call]] fanno parti di questo dato che ci pensa kernel
- Funzione non rientrante 
	- cauzione
	- un esempio sono quelle della libreria standard di C 
		- qua abbiamo anche problemi con [[Bufferizzazione]]

