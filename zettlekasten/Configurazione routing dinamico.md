Questo per [[Processo configurazione network]] 
- entrare nella cli del router 2 per attivare il RIP router
	- router rip 
	- default-information originate
	- no auto-summary
	- version 2
	- network 192.168.0.0
	- network 172.18.0.0
- Ripetere lo stesso per ogni router 
	- inserire solo quelli che sono attaccati a noi