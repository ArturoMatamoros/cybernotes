Questo è un protocollo [[Protocolli FHRP]] 

Ci devono essere almeno due router:
- uno forwarding 
- uno in Standby
Alla fine il forwarding invia un messaggio ogni 5 secondi a quello in standby. Quando questo non è più presente, nessun invio viene fatto, e quello in stand by diventa il router forwarding. 

Priorità

Va da 0 a 255 ed è default a 100. Maggiore la priorità maggiore è il diritto che hanno per andare in forwarding prima. 

Stati

Siccome è un algoritmo ci sono vari stati 
- initial 
	- cambio di configurazione 
- learn 
- listen 
- speak
- standby
- active