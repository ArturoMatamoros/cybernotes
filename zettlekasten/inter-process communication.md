[[Segnali in linux]]
## Definizione 
- abbiamo in un sistema operativo
	- processi indipendenti 
	- processi cooperanti 
- possiamo scambiare messaggi, dati, e memoria
- ci sono meccanismi diversi 
	- pipe
	- FIFO
	- Condivisione di memoria
	- segnali
	- sincronizzazione 
		- semafori 
## Pipe 
le pipe permettono di andare a scambiare dei dati basato di produttore-consumatore e per usarle usiamo read and write. 
le pipe sono un byte stream, unidirezionali e con capacità limitata
- limitazioni 
	- half-duplex leggo da una parte e scrivo nell'altra 
	- processi con antenati in comune 
	- per superare usiamo le FIFO 
- queste sono quelle che usiamo nel terminale 
	- in questo caso il terminale lo fa al posto nostro 
- per creare abbiamo S.C.  `int pipe (int filedes [2]); 
	- la pipe si invoca prima di una fork 
		- questo dato che padre e figlio possano comunicare 
- read è bloccante quindi possiamo usarla per bloccare la pipe
- se la pipe è piena allora anche la write è piena

