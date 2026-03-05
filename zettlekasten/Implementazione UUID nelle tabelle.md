Utilizzando [[Query]] noi possiamo implementare il [[UUID]]

CREATE TABLE esami(
	id VARCHAR(32),
	dataEsame VARCHAR(50),
	titoloEsame VARCHAR(50)
);

CREATE TABLE utenti (
	id BINARY(16) PRIMARY KEY,
	nome VARCHAR(100),
	creato_il TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO utenti (id, nome)
VALUES(
	UNHEX(REPLACE(UUID(),'-','')),
	'Alice'
);

SELECT HEX(id) AS uuid_hex, nome FROM utenti;