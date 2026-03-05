DORA è il nome in codice dello scambio tra computer e server. Tutto questo si usa tramite [[Broadcast]].  Questo si configura nel server stesso
- Inseriamo tutti i dati necessari
	- gateway
	- subnet mask
	- dns
- Per andare ad aggiungere un'altra pool noi dobbiamo andare a modificare e poi add
- Nel gateway dobbiamo andare anche ad inserire il helper address.

Per configurarlo: 
- Nel server inserire HTCP on
- inserire tutti i dati necessari per la pool 
- Nel ROUTER
	- interface fa0/0 
	- ip address 10.0.0.254 255.0.0.0
	- no shutdown
- Per fare si che il DHCP passi attraverso i router
	- aggiungere pool
	- Router 
	- interface fa0/1
	- ip helper-address 10.0.0.50 (indirizzo del server)
Link:  
- [[Processo configurazione network]]
- [[Dynamic Host Configuration Protocol (DHCP)]]
- [[Processo DORA]]