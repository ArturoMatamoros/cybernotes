[[Networking]]
La rete è una serie di dispositivi interconnessi, separati e autonomi. In modo tale da avere questa comunicazione sono necessarie delle regole, questi sono i protocolli per la comunicazione. Queste regole sono contenute sia nel software che nel hardware. 
Le prime regole sono state inserite nel TCP/IP. Le regole poi si sono diventate standard e queste sono le ISO/OSI. 

Bisogna tenere in mente il [[Processo di comunicazione]]

Per queste lezioni ISO/OSI = TCP/IP
- In ISO/OSI troviamo 7 livelli.
	- Ogni dispositivo lo ha ed è infatti un level 7
	- I 7 sono : 
		- 7 [[Protocolli Application]]
		- 6 [[Protocolli Presentation]]
			- questo ha cifratura e non contiene protocolli
		- 5 [[Protocolli di Session]] 
		- 4 [[Protocolli di Transport]] 
			- Questo è, insieme all'1, il più complesso, crea segmenti
		- 3 [[Protocolli Network]] 
		- 2 [[Protocollo Data link]]
			- Data link si divide in due e metà è software e l'altra hardware 
		- 1 [[Protocolli fisici]]  
- In TCP/IP (che è quello contenuto in ogni macchina)
	- Questo ha 4 livelli 
		- Application 
			- contiene 7,6 e 5
		- Transport 
			- contiene 4
		- Internet
			- Contiene 3 Network
		- Network access
			- Contiene 2 e 1 
- 