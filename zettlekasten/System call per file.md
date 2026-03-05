[[File system Linux]]
## Definizione
le system call di linux sono molto simili alle [[funzioni di libreria per file]] e sono abbastanza semplice se abbiamo [[Programmazione in C]] dato che sono creati dalla stessa persona.

le [[System call]] sono : 
- `int open(const char *pathname,int flags, mode_t mode);
	- ritorna 0 > se ha aperto il file 
	- ritorna -1 in caso di errore 
	- diamo path e dobbiamo decidere i [[Permessi Linux]]
		- `_RDONLY O_WRONLY, e O_RDWR
	- mode è opzionale 
		- questo serve per dare nulla per scontato 
		- gli andiamo a dare flag per i permessi 
		- `S_I[RWX]USR ,S_I[RWX]GRP, S_I[RWX]0TH
- `int close(int fd);
	- chiude il file 
- lseek() 
- `ssize_t read(int fd,void *buf, size_t count);
	- leggiamo fd, conta i byte e metti nel buff
	- ti da errore se -1 altrimenti è maggiore di 0
- `ssize t write(int fd, const void *buf, size_t count);
	- funziona nello stesso modo
	- ti ritorna il numero di byte da scrivere 
- `int Stat (const char *restrict pathname,struct stat * statbuf);`
	- ritorna informazione su pathname 
	- la struct stat ci dice tutto quello che dobbiamo sapere su file
	- `st_mode` ci dice i permessi e il tipo di nodo 
	- andare a vedere bene l'esempio dato che è da esame 
- `mkdir e rmdir (const char *path, mode_t mode)
	- queste funzionano come nella linea di comando 
- `int fd = open("path", O_RDONLY|O_DIRECTORY)
	- per listare ma complesso e scoraggiato 
- `#include < sys/types.h>
	`#include <dirent.h>
	`DIR * Opendir(const char *name);
	`struct dirent *readdir (DIR *dirp);
	`int closedir (DIR *dirp);
	- in questo caso abbiamo come leggere il tutto
	- vai a guardare l'esempio, non riesco a pensare. 
	- ricordiamo che fa 1 alla volta
- troviamo anche quelli che sono comandi bash
	- `ln target link_name`questo crea [[Soft e hard link]]
	- `stat path` stampa tutto quello che troviamo su un file 
	- `du directory`ottiene la dimensione della cartella

tieni conto che questo è fondamentale per l'esame. 

