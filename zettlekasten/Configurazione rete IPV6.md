[[Indirizzo IPV6]]

Creiamo una piccola rete di computer, switch e router
- Forniamo un indirizzo alla rete
- Forniamo un ipv6 ai computer
- Nel Router
	- Hostname GW6 
	- IPV6 unicast-routing 
	- interface fa0/0
	- ipv6 address 2001:DB8:ACAD:1::1/64
	- ipv6 address FE80::1 link-local
	- no shut
- Andare nel computer e mettiamo automatic
- Configuriamo il RIP in modo tale che tutto sia collegato
	- Interface fa0/0
	- ipv6 rip cisco enable
	- interface fa0/1
	- ipv6 rip cisco enable 
- Andare a collegare reti che siano ipv4 con le ipv6
	- router rip
	- version 2
	- network 170.0.0.0
- Ora [[Configurazione tunneling IPV6]]
