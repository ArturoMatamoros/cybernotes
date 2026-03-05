Come sappiamo il [[Indirizzo IPV4]]
- Classe A: 10.0.0.0 fino a 10.255.255.255. (privato)
	- nella classe A noi abbiamo da 0 a 127 reti 
		- da qui abbiamo 0.255.255.255 possibili ip interni
	- fascia 127 è local host 127.0.0.1
- Classe B: 172.16.0.0.  (privato)
	- Qua abbiamo invece 128-191 per il primo
- Classe C: 192.168.0.0. fino a 192.168.255.255. (privato)
	- 192 alla 223/24
	- Il tutto finisce con la classe C, le più numerose
	- Qui abbiamo 2 alla 24 - 2 reti. 
- Classe D: 224-239 Multicast
	- Queste ci permettono per andare a inserire indirizzi di registrazione
	- Permette andare a risparmiare spazio nella banda. 
	- 224.0.0.5 è il multicast usato da [[Protocollo OSPF]]
- Classe E: 240-255 Sperimentali

Nessuno di tutti questi può andare a viaggiare in una rete pubblica. 
