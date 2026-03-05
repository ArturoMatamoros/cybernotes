Questo è un progetto nel quale noi andiamo a creare un [[Database relazionali]] che contiene una serie di tabelle. Al loro interno abbiamo:
- Utente
	- ID : INT
	- nome : VARCHAR(50)
	- cognome : VARCHAR(50)
	- email : VARCHAR(50)
	- dataDiNascita : DATE
	- address : VARCHAR(50)
- Ordini
	- id : INT
	- idUtente : INT
	- dataOra : TIMESTAMP (2001-09-29)
	- importo : FLOAT
	- descrizione : VARCHAR(100)
	- FOREIGN KEY (idUtente)
	- REFERENCES utenti(id)
	
CREATE TABLE prodotti(
	id INT AUTO_INCREMENT PRIMARY KEY,
	 id_ordini INT,
	 nome VARCHAR(50),
	 categoria VARCHAR(50),
	 prezzo FLOAT,
	 magazzino VARCHAR(100),
	 FOREIGN KEY(id_ordini) REFERENCES ordini(id)
	 );
	

Inziamo quindi con I [[Query di base]] e andremo a chiamare il Database shop. 
Una volta fatta noi andiamo a creare le due tabelle con [[Query uso tabelle]].  

[[Query per unione tabelle]]



