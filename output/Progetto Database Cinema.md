Questo è un progetto di [[Database relazionali]] nel quale abbiamo bisogno di gestire le prenotazione dei posti. Ogni spettacolo ha:
- un numero totale di posti
- numero di posti disponibili 

Ogni abbiamo prenotazione
- è associata ad uno spettacolo 
- ha un cliente
- n posti prenotati 

Simulare due prenotazioni consecutive nella stessa transazione 
- prima valida
- seconda prenotazione errata

ESECUZIONE 
- [[Query uso tabelle]] Creazione tabella spettacolo
		CREATE TABLE spettacolo(  
		id INT AUTO_INCREMENT PRIMARY KEY,
		nome VARCHAR(50),  
		posti INT,
		posti_disponibili INT,  
		) ENGINE=InnoDB;
- creazione tabella prenotazione
		CREATE TABLE prenotazione(  
		id INT AUTO_INCREMENT PRIMARY KEY,
		id_spettacolo INT,
		nome VARCHAR(50),  
		posti_prenotati INT  
		FOREIGN KEY (id_spettacolo)  
		REFERENCES spettacolo(id)
		) ENGINE=InnoDB;
- Insert di elementi
	 INSERT INTO TABLE spettacolo (nome, posti, posti_disponibili)
	 VALUES (theweeknd, 50, 50),(thesupreme, 100, 100 );
- iniziamo Transizione [[Query transazioni]]
	- START TRANSACTION;
	- SAVEPOINT init;
- INSERT INTO prenotazione(id_spettacolo, nome, posti_prenotati)
	- VALUES (1,”Francesco”, 2);
	- UPDATE spettacolo
	- set posti_disponibili = posti_disponibili - 2
	- WHERE id=1;
	
		SAVEPOINT dopo_francesco;

	- INSERT INTO prenotazione(id_spettacolo, nome, posti_prenotati)
	- VALUES (2,”Boris”, 6);

	- UPDATE spettacolo
	- set posti_disponibili = posti_disponibili - 6
	- WHERE id=2;

		SAVEPOINT dopo_boris;

	- ROLLBACK dopo_francesco;
	- COMMIT;vla