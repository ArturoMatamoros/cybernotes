[[Programmazione in C]]
## definizione 
una libreria è una collezione di funzioni di utilizzo comune 
nel programma c si attiva con `#include <libreria>` e quelle principali sono quelle contenute nelle librerie standard. Quelle fondamentali sono: 
- stdio.h 
- stdlib.h
- math.h
- string.h
- type.h
solo nei sistemi POSIX abbiamo a disposizione delle libreria extra `<unistd.h>` che ci permette di usare system call direttamente
- Bisogna tenere attenzione con librerie e [[System call]], le librerie le usano ma non lo sono tutte, tieni conto anche del fatto che le system call non sono tutte uguali quindi non si possono usare direttamente.