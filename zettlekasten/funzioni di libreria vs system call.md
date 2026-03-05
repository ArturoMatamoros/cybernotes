[[File system Linux]]
## Definizione 
la differenza tra [[funzioni di libreria]]  e [[System call]] sono diverse. Nelle funzioni di libreria sono messe a disposizione per tutti e quello che noi abbiamo sono funzioni eseguibile in user mode. Le system call invece sono [[Kernel]], quindi qui abbiamo un [[Kernel vs User mode]]

invocare una system call significa che il nostro programma invoca il kernel grazie agli interrupt. In questo caso la system call va a chiamare il kernel in modo tale da andare a svolgere la azione desiderata.

quindi il processo è questo, chiamiamo nel programma, usiamo `syscall` in assembly, vado a chiamare il kernel, risolviamo il problema e torniamo indietro. 

il manuale linux è ottimo per andare a capire il tutto 

abbiamo strumenti di debug e utilizziamo 
`strace`non richiede di ricompilare i programmi, è una lista di andare a vedere le system call che vengono utilizzate e con questo le possiamo anche capire se un programma è un virus in base alle s.c.
`ltrace` invece va a darci le funzioni di libreria.
