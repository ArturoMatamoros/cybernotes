Il three-way handshake è un metodo che garantisce la comunicazione efficace all'interno del protocollo TCP presente nei [[Protocolli di Transport]]. 
Questo consiste nel comunicare grazie ai segnali: 
- syn, dove si cerca di comunicare.
- syn ack, dove si risponde sia che si sta comunicando sia che abbiamo ricevuto il pacchetto precedente.
- ack, dove il client conferma 

Per concludere la comunicazione usiamo:
- fin
- fin, ack
- ack (non sempre necessario) 
