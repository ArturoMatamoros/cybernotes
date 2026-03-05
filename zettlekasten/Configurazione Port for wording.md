Partendo da un progetto con [[Configurazione NAT]] presente e funzionante iniziamo dalla configurazione port for wording. 

- nel gateway 
	- ip nat inside source static tcp 10.0.0.200 (porta del computer) 80 50.0.0.1 (gateway) 8080 
	- il TCP dipende dalla porta da noi scelta
- Andiamo nel server .200 e andiamo ad inserire il nostro servizio https
	- Da un server in 70.0.0.0 dovrebbe essere disponibile 
