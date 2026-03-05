[[Problematiche dischi]]
## Definizione 
Le tecniche RAID (redundant array of independent disks)
hanno lo scopo di affrontare i problemi di prestazioni e
affidabilità

questo ci permette di avere famiglia di dischi, si basa su striping.
- distribuire bit/byte 
- distribuire [[Allocazione blocchi nel disco]] 
	- queste sono le più usate 

bisogna anche aggiungere codici di parità per proteggere errori

I livelli di raid sono: 
- RAID0 
	- divisione con striping basilare su 2 dischi
	- veloce ma poco affidabili 
- RAID1 mirroring 
	-  dati replicati su più dischi 
	- lento ma affidabile 
- RAID4 disco di parità 
	- minimo 3 dischi 
	- striping su N-1 dischi 
	- ultimo disco contiene la parità
	- questo approccio è veloce e affidabile 
	- ma nella scrittura bisogna aggiornare la parità e quindi è inefficiente dato il costante cambiamento di essa
- RAID5 parità distribuita 
	- uguale al precedente ma la parità è distribuita.
	- tutti i vantaggi nessun svantaggio se non scrittura parità
	- Questo è quello più utilizzato 
- RAID 6 doppia parità distribuita 
	- uguale alla 5 ma più lenta con 2 parità

il limite di tutto questo sono  [[file system distribuiti]] 


