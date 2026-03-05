[[Virtual LAN (VLAN)]]
- CREARE LA VLAN
	- vlan 10 (numero)
	- nome AMMINISTRAZIONE 
	- controlla che siano tutte apposto (non sono in run. conf. )
		- sh vlan
- Assegnare le porte 
	- interface range fa0/1-8
	- switchport mode access
	- switchport access vlan 10
- eliminare le porte non in uso 
	- interface range fa0/21-23
	- shutdown
- andare a configurare porta management
	- interface vlan 40 
	- ip address 172.17.0.50 255.255.0.0
- Ora [[Configurazione SSH sui dispositivi]] 
- Andiamo a fare il trunk con un'altro switch [[Configurazione trunk]] 


Link: 
- [[Processo configurazione network]]
- [[Configurazione VTP]]
- [[Configurazione Inter VLAN routing]]