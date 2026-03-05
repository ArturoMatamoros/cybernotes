[[Protocolli ISO-OSI]]
Qui abbiamo un insieme di protocolli in cui andiamo ad aggiungere informazioni in testa ai pezzi divisi dal [[Protocolli di Session]]. La informazione che aggiungiamo sono le Porte varie che identificano : 
- Porta destinazione (porta 80 in server web) 
	- Ci dice esattamente a quale servizio dobbiamo inviare la informazione
		- si distingue dal [[IP address]] nel fatto che qui noi abbiamo il programma esatto, non solo la posizione del computer. 
- Porta sorgente
	- separare i flussi, infatti esso è l'identificativo di ogni porta sul nostro dispositivo
	- è un numero casuale e identificativo

Alcuni protocolli, che hanno porte come visto prima, che utilizziamo sono: 
- [[TCP (Transmission Control Protocol)]]
	- Orientato alla connessione con [[Three-way handshake]]
	- ritrasmette in caso di errore
		- ritrasmette i segmenti mancanti dopo un time-out
	- Controllo del flusso 
		- quando vediamo che il flusso è troppo veloce per colui che riceve allora TCP capisce quando andare  a migliorare il tutto. 
- [[UDP (User Datagram Protocol)]]
	- Non orientato alla connessione 
	- molto semplice, non gli importa tutto il metodo di prima.  
	- non numera i segmenti 
	- non ritrasmette in caso di errore           