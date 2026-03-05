[[Dischi e file system]]
## Definizione 
il [[File system]] si occupa di mappare accessi a file e directory nei blocchi e uno dei problemi è la allocazione. 

Ogni blocco viene dato a ogni file, quando il file non si riempie abbiamo la **Frammentazione interna

abbiamo quindi: 
- **Allocazione contigua**
	- ogni file ha blocchi continui e dobbiamo sapere 
		- dove inizia e quanto dura
	- Problema! **Frammentazione esterna**
		- quindi non ci sono abbastanza spazi contigui
- **Locazione concatenata
	- ogni file ha anche dove trovare il blocco seguente.
		- facciamo una catena di file.
	- problema! **Inefficiente** e **Se una si rovina BYE**
- **File allocation table(FAT)
	- nei primi blocchi del disco contengono una lista
		- ogni una di questa ha la lista del programma
	- problema! **rotta la fat butti via il disco 
- **Allocazione indicizzata 
	- fai il blocco indice e ti dice i pezzi.
	- problema! **spreco
- **Allocazione combinata
	- si usa **[[Inode]]** 
		- contiene metadati
		- i numeri dei primi 12 blocchi 
		- puntatori indiretti (blocco indice)
			- possiamo avere un indice degli indici in caso

### Correlati 
[[RAID]]


