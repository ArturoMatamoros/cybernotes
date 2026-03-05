[[Linux]]
## Utenti 
In Linux abbiamo:
- Utenti UID
	- ogni uno ha una cartel [[File system]] chiamata home directory
- Gruppi GID
	- ogni utente deve avere almeno un gruppo
	- Questo è automaticamente il nome del user se non cambiato
	- Ogni uno ha un Gruppo primario
	- Puoi avere 0 o più Gruppi secondari 
- [[Utente root]]: Questo esiste sempre e ha tutti i privilegi e bypassa i [[Permessi Linux]]
per la loro gestione utilizziamo alcuni sono [[Comandi utenti]] e [[Comandi permessi Linux]]

ricordiamo che ogni file ha un gruppo e utente proprietario.

Gli utenti nel [[File system Linux]] sono contenuti in `/etc/passwd`

