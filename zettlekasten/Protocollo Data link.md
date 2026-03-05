[[Protocolli ISO-OSI]] 
Serve a [[Protocolli Network]] e quindi sa di sicuro che hanno un [[IP address]].
Qui aggiungiamo elementi in testa e in coda che servono al movimento fisico tramite un metodo chiamato Hop-by-hop. Questi, alla fine, sono chiamati Frames.  Abbiamo in testa:
- MAC S (sorgente) e MAC D (destinazione)
	- Questi [[MAC Address]] sono fisici (sono unici e non si possono cambiare, se non manualmente) 
	- Flat perché non contengono informazioni sul server.
		- Bisogna quindi aggiornare i passi fisicamente, hop-by-hop
	- se gli [[IP address]]  ipv4 e ipv6 è dove parto e dove arrivo qui vado a fare un passo alla volta. 

[[Termini fondamentali Data-Link]]
[[Protocollo ARP]] 
[[Protocollo Spanning tree]]  

Alla fine del tutto noi andiamo ad inserire un dato alla fine del pacchetto in modo tale da concludere il Frame. Quello che mettiamo in coda è un Frame Check, quindi un controllo della qualità del file. Simile al [[Parity bit]]. 