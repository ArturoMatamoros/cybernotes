[[File system Linux]]
## Definizione 
la bufferizzazione è il processo che le [[funzioni di libreria per file]] utilizzano in modo tale da non dover invocare ogni singola volta una system call. Queste infatti scrivono in memoria e dopo di che questo andiamo a scrivere tutto insieme.

Su [[Linux]] abbiamo 8192 but per buffer ed è possibile cambiarla con: 
```C
void setbuf(FILE *stream, char *buf); 
```
### Correlati 
- [[Programmazione in C]]
- [[System call]]