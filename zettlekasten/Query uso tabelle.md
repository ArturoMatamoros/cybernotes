[[Query]]

CREATE TABLE studenti(
	id INT AUTO_INCREMENT PRIMARY KEY, ([[Chiavi nei database]])
	nome VARCHAR(50),
	cognome VARCHAR(50),
	eta INT,
	email VARCHAR(100)
) ENGINE=InnoDB; 

INSERT INTO esami (id, dataEsame, titoloEsame) 
VALUES (uuid(), "05/12/2026","Esame Database");

INSERT INTO prodotti(id_ordini, nome, categoria, prezzo, magazzino)
VALUES (2, "BBQ HONEYCOMB", "BBQ", 199.99, "UDINE(UD)"),
	    (16, "HU HU HONEY", "CARBONE", 24.99, "DUINO(TS)"),
	    (19, "HONEY, HONEY, BBHONEY", "STICKER", 24.99, "DUINO(TS)");

Quando abbiamo una foreign key noi andiamo ad aggiungere:
CREATE TABLE studenti(
	id INT AUTO_INCREMENT PRIMARY KEY, ([[Chiavi nei database]])
	classeID INT,
	nome VARCHAR(50),
	cognome VARCHAR(50),
	eta INT,
	email VARCHAR(100)
	FOREIGN KEY (chiave secondaria in questa tabella)
	REFERENCES tabella(id)
); 

Link: 
- [[Query per unione tabelle]]
- [[Implementazione UUID nelle tabelle]]