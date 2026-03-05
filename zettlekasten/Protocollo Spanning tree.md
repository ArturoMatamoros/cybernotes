Questo è parte del [[Protocollo Data link]] e fondamentale per Switch in [[Tipi di Intermediate devices]] 
- Questo perché abbiamo 30 sec in cui lo switch non è disponibile 
	- questo per verificare che non ci siano cicli chiusi
- Quando questo accade noi andiamo a collegare un altro cavo
	- Questo è un cavo che ci permette [[Ridondanza]] 
- Questo serve ad eliminare il [[Broadcast storm]] ed qualsiasi [[Ciclo infinito]]

Ci sono vari modi in cui il tutto funziona. 
- abbiamo prima di tutto un grafo
- dopo noi andiamo a trovare uno switch principale 
- chiamiamo bridge lo switch più importante, il root bridge
- andiamo a calcolare il percorso più efficiente 
- eliminare (bloccare) le porte ridondanti creando attivamente un albero

All'interno delle porte chiuse noi possiamo anche andare a fornire delle informazioni attraverso pacchetti BPDU (Bridge Protocol data units) che aiutano a coordinare la struttura dell'albero. Questi pacchetti hanno: 
- bridge ID (serve ad identificare lo switch che invia la informazione) 
	- questo contiene una priorità, extended system id, mac address
- Priorità del bridge
	- tutti hanno una priorità di base di 32768
		- range 0 a 61440 dove 0 è maggiore priorità

Una volta stabilito il root bridge noi dobbiamo determinare il percorso migliore. Le informazioni di percorso è un internal root path cost ed è determinata dalla somma di tutti i costi e viaggiano attraverso i bpdu. Tiene conto anche dalla bandwith, più alta è più basso sarà il costo. Teniamo anche conto delle root port e anche porte designated. Queste sono anche porte di backup. 

Ora vediamo il problema per quando noi abbiamo costi uguali. Nella nostra topologia andiamo sempre a scegliere sempre il vicino con costo più basso. Abbiamo anche i casi in cui abbiamo due collegamenti e noi andiamo due collegamenti tra due switch con stesso costo, solo una può diventare una root port, infatti qua abbiamo anche una contesa tra le porte. 

Timer e stati delle porte: 
- Hello timer sono per default ogni due secondi e servono a capire se si è ancora attivo 
- forward delay timer, ogni quindici secondi, learning e listening (30 secondi)
- max age timer, se non si riceve un hello abbiamo 20 secondi prima di cambiare port
   
Per risolvere il problema del fatto che lo spanning tree abbia un wait di 30 secondo noi possiamo andare a determinare che alcuni link siano riservati esclusivamente a computer e non a switch. 