[[Processo configurazione network]]
Prima di tutto quello di cui abbiamo bisogno per [[server TFTP]]
- Configurare il defult gateway per gli switch 
	- ip default-gateway 10.0.0.254
- Configurare all'interno del server che il servizio sia on 
- nello switch e router configurato andiamo in cli
	- copy start tftp
	- inserire l'indirizzo 
- Copiare file IOS del file, su swa andiamo su cli
	- show flash (per ricevere il ios)
	- copy flash tftp
	- inserisci il nome del file
	- inserisci il server
	- nominare SWA-IOS


Per il backup invece bisogna fare altro.