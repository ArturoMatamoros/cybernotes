Questa è la configurazione [[Router]] iniziale. 
- Entrare in conf t 
- Cambiare il nome 
	- hostname gateway (qualsiasi cosa)
- Nome del dominio (necessario per [[SSH]])
	- ip domain-name cisco
- Impostazione di IP per ogni rete che noi colleghiamo 
	- GATEWAY(config-if)#interface fa0/1 
	- GATEWAY(config-if)#ip address 172.16.0.254 255.255.0.0
	- GATEWAY(config-if)#no shut
Link: 
- [[Processo configurazione network]]