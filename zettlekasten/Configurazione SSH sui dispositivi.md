Questo ci serve per configurare una configurazione [[SSH]] con vari [[Tipi di Intermediate devices]]. I passaggi sono: 
1. Fornire al dispositivo un nome 
	-  switch(config)# hostname SWA
2. Impostare un nome di dominio 
	-  SWA(config)# ip domain-name cisco
3. Creare le chiavi crittografiche
	- swa(config)# crypto key generate rsa
4. Creare database di utenti
	- Swa(config)# username utente1 password 1234
5. Impostare come unico protocollo ammesso SSH
	- swa(config)# line vty 0 15
	- swa(config-line)# password cisco
	- swa(config-line)# login local (punto successivo)
	- Swa(config-line)# transport input SSH 
6. Impostare la verifica credenziale su database locale 
	- swa(config-line)# login local
- Ricorda la pasword di enable 