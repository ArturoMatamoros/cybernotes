[[Segnali in linux]]
[[Bash e Shell]]
## Segnali  
-  kill PID 
	- manda sigterm 
	- abbiamo anche -KILL -INT 
	- abbiamo anche killall e pkill
- ctrl+c abbiamo SIGINT (interrupt)
- SIGQUIT simile a sigint ma fa anche un dump
- ctrl+z abbiamo SIGSTOP mentre l'altro SIGSTP lo da solo il kernel
	- una volta fatto questo noi abbiamo
		- fg per foreground 
		- bg per background
- SIGCONT continue.
	- Questo avviene dopo uno stop
	- ma attenzione che questo non riceve altro segnale se non questo
- ./programma & 
	- va a svolgere in background 
- nohup ./programma 
	- questo va a mandare avanti il tutto anche quando stacchi il terminale, ma tutti usano il comando screen 
- trap command SIGNAL 
	- qua esegue il comando arrivato signal 
	- possiamo anche usarlo anche con la EXIT 
		- questo lo usiamo quando abbiamo script bash
		- serve per la pulizia del programma. 