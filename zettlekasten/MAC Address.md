Il mac address è un indirizzo scritto in linguaggio esadecimale che identifica ogni scheda Rete. I MAC Address sono fondamentali nel [[Protocollo Data link]]. Questi possono essere usati per la [[Sicurezza rete wireless]]. 

I mac address possono comunque essere modificato. Gli [[Hypervisor]] tendono a fare questa modifica. Noi possiamo farlo con 

``` bash
ifconfig eth0 hw mac 38:38:38:38:38:38
```
Ma attenzione, anche se la rete in bridge, con l'Hypervisor, il tutto non funziona veramente quando si esce in rete. Ma in un computer linux vero e proprio questo funzione. 

Tutto questo serve per andare a cambiare il mac in caso di clonazione di macchina virtuale. [[Change Mac-Address]]. 