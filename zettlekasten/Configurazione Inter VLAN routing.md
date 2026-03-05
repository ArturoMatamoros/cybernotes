[Inter VLAN routing]]

ora configuriamo quello normale
- Dopo aver fatto la [[Creazione VLAN]] noi abbiamo più reti
- ora dobbiamo collegarle con il router in modo tale che comunichino tra loro 
- andiamo ad inserire il gateway e mettiamo una porta wick 2enet
- Andiamo a collegare 1 cavo per vlan al router
	- qua abbiamo 4 cavi che vanno dalla ultima interfaccia
- andiamo ad attivare sullo switch la interfaccia 24 con rete 40
- Andiamo sullo switch e configuriamo le reti 
	- interface fa0/0
	- ip address 10.0.0.254 255.0.0.0
	- (così per tutto)



Configuriamo un ROUTER ON A STICK 
- ora noi andiamo a [[Configurazione trunk]] da switch a router nella porta gigabit
- ora andiamo sul router 
	- interface g0/0
	- no shut
- andiamo a configurare il tutto 
	- interface g0/0.10 
	- encapsulation dot1q 10
	- ip address 10.0.0.254 255.0.0.0
	- (ripeti per ogni vlan)


Ora andiamo a cambiare e configurare un LAYER 3 SWITCHING 
- inseriamo un 3650, un layer 3 switch 
- qui non usiamo canali di trunk quindi andiamo diretti sullo switch layer 3
- andiamo ad inserire la scheda per il power on 
- andiamo ad eliminare il warning 
	- no cdp run
- Andiamo a dargli la possibilità di essere un router
	- ip routing 
- andiamo a creare le vlan 
	- vlan 10
	- name AMMINISTRAZIONE
- andiamo a mappare tutto 
	- interface g1/0/1 
	- switchport mode access
	- switchport access vlan 10 
- Andiamo a dare indirizzo ip alle reti 
	- interface VLAN10
	- ip address 10.0.0.254 255.0.0.0