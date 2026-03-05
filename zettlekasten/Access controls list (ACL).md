Questo è un contenitore di controlli che ci controllano gli accessi a determinati punti. Ogni istruzione viene eseguita in ordine e vengono scritti in modo chiaro come una serie di regole (trovi nel [[Configurazione NAT]]). Questo ci permette di capire come funziona il [[Firewall]]. 

queste si dividono in due tipi: 
- standard 
	- vanno da 1-99
- extended 
	- vanno da 100-199
	- il primo comando è questo
		- access-list 100 
		- permit tcp (il protocollo, protocolli, che vogliamo permettere)
		- 10.0.0.0 0.255.255.255 (indirizzi ip da permettere)
		- host 90.0.0.100 (il numero del server tcp)
		- eq 80 (porta 80, un sito web http) eq www (per essere più generali) 
	- access-list 100 permit udp 20.0.0.0 0.255.255.255 host 90.0.0.101 eq 53 (DNS)
		- immaginiamo che sia un deny, questo significa che non possiamo mai contattare questi dispositivi. Miraccomando, se tutto è deny allora il resto deve essere libero altrimenti non si esce. 
	- access-list 100 permit ip any 90.0.0.0 0.255.255.255 


Access List named 
- risolve il problema di scrivere manualmente e modificare le acl e ad averle in modo chiaro e preciso. Come se non bastasse qui ogni riga è divisa da una serie di righe che noi possiamo andare a riempire. 
	- ip access-list extended MIEREGOLE 
	- deny tcp 10.0.0.0 0.255.255.255 host 90.0.0.100 eq 80
	- deny udp 20.0.0.0 0.255.255.255 host 90.0.0.101 eq 53
	- permit ip any 90.0.0.0 0.255.255.255 
- Per andare ad inserire un nuovo pezzo bisogna fare: 
	- ip access-list extended MIEREGOLE 
	- 25 (POSIZIONE RIGA) deny tcp 30.0.0.0 0.255.255.255 host 90.0.0.100 eq 80