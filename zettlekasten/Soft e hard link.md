[[Link (hard & soft)]]
## definizione 
Ci sono due tipi di link: 
- Soft link 
	- copia il path e se cambia l'originale diventa obsoleto 
	- sono shortcut per un file o una directory
		- quando abbiamo un path lungo lo riduciamo
	- `int symlink(Const char *target, const char(Linkpath);`
		- questa è la [[System call]]
	- posso anche creare anche soft link a cartelle
- Hard link
	- associa un secondo path e se il primo cambia rimane intatto
	- in questo caso punta ad un [[Inode]] che è lo stesso dell'originale
		- un hard link non può essere invalido. 
	- per eliminare nel inode ha un reference count ha il numero di link verso l'inode. 
	- non facciamo hard link a cartelle 
		- un esempio di hard link a cartella ha hard link al padre 
	- ricorda come sono [[Allocazione blocchi nel disco]] per gli inode

quando andiamo a rimuovere file con unlink ora lo capiamo.