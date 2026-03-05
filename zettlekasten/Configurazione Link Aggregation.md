[[Link aggregation]]

Qui andiamo ad usare la versione cisco degli [[AutoNegotiation protocols]] 

- Andiamo nello SWA
	- interface range fa0/1-3
	- channel-group 1 mode on 
	- exit
	- interface po1 
	- switchport mode trunk 
- Andiamo sullo SWB
	- interface range fa0/1-3 
	- channel-group 1 mode on 
	- (per qualche ragione non mette su il trunk automatico)
		- configuriamo manualmente come prima
- Creiamo e colleghiamo SWC con GB e andiamo a configurarlo ma su desirable
	- di conseguenza colleghiamo con SWA e rifacciamo ma su auto