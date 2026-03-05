
- unico applicativo
- il cliente può visualizzare il conto tramite un unico login

Bisogna
- tabelle dei vari conti correnti
- autenticazione utenti
- Gestire i permessi dei vari utenti
- L'unico al gestire il tutto sarà il banchiere
- L'auditor è l'unico ad avere i permessi di visualizzazione del log
- tenere traccia del cambio dei dati
	- quindi usare [[Trigger]] 



CREATE TABLE conto(
	id INT AUTO_INCREMENT PRIMARY KEY,
	id_utente INT, 
	nome VARCHAR(50),
	cognome VARCHAR(50),
	saldo DECIMAL(10,2)
); 