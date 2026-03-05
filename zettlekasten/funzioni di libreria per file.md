[[File system Linux]]
## definizione 
quando siamo in [[File in C]] nel [[Programmazione in C]] ricordiamo che esse sono disponibili con `libc` e sono accessibili in qualsiasi SO.

Ricordiamo che quando leggo e scrivo un file vado a muovere il cursore e questo si sposta in base a quello che abbiamo letto.
- `int fseek(FILE *fp, long distanza, int partenza)`
	- questo va a spostare il cursore
		- abbiamo SEEK_SET/CUR/END 
- `fread` e `fwrite` sono funzioni per file binari 
	- ignorano tutto 
	- leggi/scrivi nella memb oggetti, ognuno grande size byte dal puntatore a file stream e scrivili/leggili da ptr .
	- sono utili quando vogliamo andare a leggere in binario
- [[Bufferizzazione]]
- `int remove(const char *pathname);`
### Correlato 
- quando siamo su linux possiamo anche usare [[System call per file]]
- [[funzioni di libreria]]
- [[File system]]
