Parte fondamentale di [[Protocolli Network]]. Permettono ai [[Router]] di scambiarsi informazioni nelle reti conosciute e instradarle nel modo migliore.
Abbiamo due metodi: 
- IGP (Interior gateway protocols) interni sistemi autonomi
	- distance vector 
		- RIP
			- conta i salti minimi (l'unico banale ma ormai antico)
			-  I router comunicano tra di loro in modo tale da avere una tabella di router nella quale noi possiamo trovare il miglior percorso fino ad un determinato server. 
		- IGRP
	- link state
		- OSPR
		- IS-IS
	- hybrid 
		- eigrp
- EGP (Exterior gateway protocols)  per comunicare tra sistemi autonomi
	- path vector
		- BGP