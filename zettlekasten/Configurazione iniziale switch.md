[[Tipi di Intermediate devices]]
1. Apri e collega lo switch
2. Accedi tramite terminale
3. Modalità privilegiata 
4. Configura nome dello switch 
	- hostname SWA
5. Impostazione di password 
		Switch01(config)# enable secret class
	- Password connessione 
		Switch01(config)# line console 0
		Switch01(config-line)# password cisco
		Switch01(config-line)# login
		Switch01(config-line)# exit
	- Configurazione wireless
		Switch01(config)# line vty 0 15
		Switch01(config-line)# password cisco 
		Switch01(config-line)# login
		Switch01(config-line)# exit
6. Configurazione VLAN 
		Switch01(config)# interface vlan 1
		Switch01(config-if)# ip address 192.168.1.2 255.255.255.0
		Switch01(config-if)# no shutdown
		Switch01(config-if)# exit

Link: 
- [[Processo configurazione network]]
- [[Configurazione DHCP]]
- [[Configurazione Router]]
- [[Virtual LAN (VLAN)]]