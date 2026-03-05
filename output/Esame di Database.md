	[[Database]]

**12. Gestione accessi a una struttura**

Scrivi il codice SQL per la creazione di un database per la gestione degli accessi tramite PIN a una struttura.  
Il database deve soddisfare i seguenti requisiti:

- Memorizzare gli utenti autorizzati ad accedere alla struttura.  
- Per ogni utente devono essere salvate le informazioni necessarie all’identificazione e il PIN di accesso.  
- Il database deve prevedere diverse aree della struttura (ad esempio: ingresso, uffici, magazzino, area riservata).  
- Ogni utente può essere autorizzato ad accedere solo ad alcune aree.  
- Per garantire una maggiore sicurezza, è necessario implementare una tabella di auditing che deve registrare automaticamente tutte le modifiche effettuate sugli utenti contenuti nel database.
--- 
CREATE TABLE aree (
	id INT AUTO_INCREMENT PRIMARY KEY,
	nome VARCHAR(50) 
)

CREATE TABLE utenti (
	id INT AUTO_INCREMENT PRIMARY KEY,
	nome VARCHAR(50) NOT NULL,
	pin_hash CHAR(128) NOT NULL,
	pin_salt VARCHAR(50) NOT NULL
)

CREATE TABLE utente_area (
	id INT AUTO_INCREMENT PRIMARY KEY, 
	id_utente INT,
	id_area INT
	FOREIGN KEY (id_utente) REFERENCES utenti(id),
	FOREIGN KEY (id_area) REFERENCES aree(id)
)

CREATE TABLE audit_utenti (
	id INT AUTO_INCREMENT PRIMARY KEY, 
	user_id INT NOT NULL, 
	nome_utente VARCHAR(50) NOT NULL,
	pin_hash_precedente CHAR(128) NOT NULL,
	pin_salt_precedente VARCHAR(50) NOT NULL,
	operazione VARCHAR(50),
	eseguito_da VARCHAR(50)
) 

DELIMITER // 

CREATE TRIGGER update_utenti
AFTER UPDATE ON utenti
FOR EACH ROW 
BEGIN 
	INSERT INTO audit_utenti(
		user_id,
		nome_utente,
		pin_hash_precedente,
		pin_salt_precedente 
		operazione,
		eseguito_da
	)
	VALUES(
		OLD.id,
		OLD.nome,
		OLD.pin_hash, 
		OLD.pin_salt, 
		"UPDATE UTENTI", 
		USER()
	);

END //

DELIMITER ; 























CREATE DATABASE azienda; 
USE azienda; 

CREATE TABLE magazzino(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	altre_informazioni VARCHAR(50)
)

CREATE TABLE area_riservata(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	altre_informazioni VARCHAR(50)
)

CREATE TABLE uffici(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	altre_informazioni VARCHAR(50)
)

CREATE TABLE ingresso(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	altre_informazioni VARCHAR(50)
)

CREATE TABLE utenti(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	nome_utente VARCHAR(50),
	password VARCHAR(50),
	ruolo VARCHAR(50)
) 

-- tutte le password(pin) verranno poi criptati attraverso MD5 durante l'insert

CREATE TABLE audit_utenti(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	nome_utente VARCHAR(50),
	password VARCHAR(50),
	ruolo VARCHAR(50),
	operazione VARCHAR(50),
	eseguito_da VARCHAR(50)
) 


CREATE USER "tecnico"@"10.0.0.2" IDENTIFIED BY "password_forte"; 
GRANT SELECT, UPDATE TO "tecnico"@"10.0.0.2" ON area_riservata WITH GRANT OPTION; 
GRANT SELECT,  UPDATE TO "tecnico"@"10.0.0.2" ON uffici;

CREATE USER "magazziniere"@"192.16.9.* " IDENTIFIED BY "PASSWORD"
GRANT SELECT TO "magazziniere"@"192.16.9.* " ON magazzino; 

CREATE USER "risorse_umane"@"10.0.9.* " IDENTIFIED BY "password_forte"
GRANT SELECT TO "risorse_umane"@"10.0.9.* " ON ufficio; 
GRANT SELECT TO "risorse_umane"@"10.0.9.* " ON area_riservata; 

CREATE USER "auditor"@"localhost" IDENTIFIED BY "password_forte";
GRANT SELECT TO "auditor"@"localhost" ON "audit_area_riservata"; 
GRANT SELECT TO "auditor"@"localhost" ON "audit_uffici"; 

DELIMITER //
CREATE TRIGGER update_utenti
AFTER UPDATE ON utenti
FOR EACH ROW
BEGIN
    INSERT INTO audit_utenti(
        id,
        nome_utente, 
        password,
        ruolo,
        operazione,
        eseguito_da
   )
    VALUES ( 
	 OLD.id,
	 NEW.nome_utente,
	 NEW.password,
	 NEW.ruolo,
        'UPDATE DATO', 
        USER()        
    );
END //
DELIMITER ;



**13. Livelli di accesso e controllo degli ingressi**

A integrazione dell’esercizio precedente, estendi il database MySQL implementando una gestione dei livelli di accesso al database, al fine di garantire una corretta separazione dei privilegi.  
Devono essere definiti tre livelli di accesso distinti:

- Utente di sistema: Utilizzato dal sistema automatico che rileva l’apertura delle porte.  
- Responsabile della gestione degli utenti: Può aggiungere, modificare ed eliminare utenti e assegnare i relativi permessi di accesso alle aree.  
- Utente di auditing: Può consultare lo storico delle modifiche effettuate sugli utenti, ma non può modificarle.

Per ciascun livello devono essere definiti utenti MySQL e permessi appropriati, applicando il principio del minimo privilegio.  
Implementa in fine una funzione (o procedura) che:

- Riceva in input: un PIN, una area/stanza della struttura- Restituisca: 1 se l’accesso è consentito, 0 se l’accesso non è consentito
--- 
CREATE USER 'system_user'@'10.0.0.2' IDENTIFIED BY 'password'; 
GRANT EXECUTE ON PROCEDURE accesso_consentito TO 'system_user'@'10.0.0.2'; 
FLUSH PRIVILEGES;

CREATE USER 'responsabile_utenti'@'10.0.0.1' IDENTIFIED BY 'password';
GRANT INSERT,SELECT,DELETE,UPDATE TO 'responsabile_utenti'@'10.0.0.1' ON utenti;
GRANT INSERT,SELECT,DELETE,UPDATE TO 'responsabile_utenti'@'10.0.0.1' ON utente-area;
FLUSH PRIVILEGES; 

CREATE USER 'auditor'@'localhost' IDENTIFIED BY 'password';
GRANT SELECT TO 'auditor'@'localhost' ON audit_utenti;
FLUSH PRIVILEGES; 

DELIMITER // 

CREATE PROCEDURE accesso_consentito (
	IN pin VARCHAR(50),
	IN area VARCHAR(50)
)
BEGIN
	
DELIMITER //

CREATE PROCEDURE accesso_consentito (
    IN p_pin VARCHAR(50),
    IN p_area VARCHAR(50)
)
BEGIN
      
END//

DELIMITER ;
























Considero la parte precedente non del tutto collegata, sopratutto nella creazione di utenti e i grant. 

CREATE USER "user"@"localhost" IDENTIFIED BY "password"

CREATE USER "responsabile"@"10.0.0.1" IDENTIFIED BY "password"; 
GRANT SELECT, INSERT, UPDATE TO "responsabile"@"10.0.0.1" ON utenti WITH GRANT OPTION; 

CREATE USER "auditor"@"localhost" IDENTIFIED BY "password";
GRANT SELECT TO "auditor"@"localhost" ON audit_utenti; 

CREATE TABLE accessi(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	ruolo VARCHAR(50),
	database VARCHAR(50),
	accesso INT
) 

-- Qui inserisco i 3 utenti e il database, se ci possono accedere inserisco 1 in accesso 0 altrimenti

DELIMITER //

CREATE PROCEDURE check_access(
	IN p MD5_pin(),
	IN a VARCHAR(50)
)
BEGIN 
	SELECT accesso
	FROM utenti, accessi 
	WHERE utenti.password = p
	AND accessi.database = a
	AND utenti.ruolo = accessi.ruolo
END //

DELIMITER ; 




## **Esercizio B – Gestione utenti, ruoli e privilegi di un sistema informatico**

Scrivi il codice SQL per la creazione di un database MySQL per la gestione degli utenti di un sistema informatico aziendale.
Il database deve soddisfare i seguenti requisiti:
- Memorizzare gli utenti del sistema con:
    - username
    - password (hashata)
    - stato dell’account (attivo/bloccato).
- Il sistema prevede più **ruoli** (es. admin, operatore, consulente).
- Ogni ruolo ha associati diversi **permessi** (es. lettura dati, inserimento dati, modifica dati).
- Un utente può avere **uno o più ruoli**.
- Deve essere possibile sapere **quali permessi** possiede un utente in modo indiretto tramite i ruoli.


CREATE TABLE utenti(
	id INT AUTO_INCREMENT PRIMARY KEY,
	username VARCHAR(50) NOT NULL UNIQUE,
	password CHAR(32) NOT NULL,
	stato VARCHAR(50) 
); 

CREATE TABLE ruoli(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	ruolo VARCHAR(50),
	permessi VARCHAR(50)
);

CREATE TABLE utente_ruoli(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	id_utente INT,
	id_ruolo INT,
	FOREIGN KEY (id_utente) REFERENCES utenti(id),
	FOREIGN KEY (id_ruolo) REFERENCES ruoli(id)
); 
### Parte 2 – Auditing
- Implementare una tabella di auditing che registri automaticamente:
    - modifiche alle credenziali degli utenti
    - cambi di ruolo
- Il log deve contenere:
    - utente modificato
    - tipo di modifica
    - data e ora
    - utente MySQL che ha eseguito l’operazione.

CREATE TABLE audit_modifiche(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	id_utente INT, 
	modifica VARCHAR(50),
	fatto_da VARCHAR(50)
	FOREIGN KEY (id_utente) REFERENCES utenti(id)
)

DELIMITER //

CREATE TRIGGER modifica_utente
AFTER UPDATE ON utenti
FOR EACH ROW 
BEGIN
INSERT INTO audit_modifiche(
	id_utente,
	modifica,
	fatto_da,
) VALUES (
	OLD.id,
	"update username",
	USER() 
);
END //

DELIMITER ;

### Parte 3 – Gestione utenti MySQL
Definire tre utenti MySQL con privilegi distinti:
- **Sistema applicativo**
    - può solo leggere utenti, ruoli e permessi
    - può inserire record nel log accessi
- **Amministratore**
    - può creare, modificare ed eliminare utenti
    - può assegnare ruoli
- **Auditor**
    - può solo leggere i dati di auditing
    - non può modificare nulla
Applicare rigorosamente il **principio del minimo privilegio**.

``` sql
CREATE USER sistema_applicativo IDENTIFIED BY "password"; 
GRANT SELECT TO sistema_applicativo ON utenti; 
GRANT SELECT TO sistema_applicativo ON ruoli; 
GRANT EXECUTE PROCEDURE TO sistema_applicativo ON check_permesso; 

CREATE USER amministratore IDENTIFIED BY "strongPassword";
GRANT SELECT,UPDATE,DELETE,CREATE TO amministratore ON utenti; 
GRANT SELECT,UPDATE,DELETE,CREATE TO amministratore ON utente_ruoli; 

CREATE USER auditor IDENTIFIED BY "qwerty";
GRANT SELECT TO auditor ON utenti; 
```
### Parte 4 – Funzione
Implementare una funzione che:
- Riceva in input:
    - username
    - nome di un permesso
- Restituisca:
    - `1` se l’utente possiede quel permesso
    - `0` altrimenti

```SQL

DELIMITER //

CREATE PROCEDURE check_permesso(
	IN u VARCHAR(50),
	IN permesso VARCHAR(50),
	OUT esito INT
)
BEGIN
	SELECT COUNT(*) INTO cnt
	FROM utenti u
	JOIN utente_area ut ON u.id = ut.id_area
	JOIN permesso_area pa ON ut.id_area = pa.id_permesso
	JOIN permesso p ON pa.id_permesso = p.id
	WHERE u = u.utente
	AND permesso = p.permesso;
	
	IF cnt > 0 
		SET esito 1;
	ELSE 
		SET esito 0;
	END IF
END //

DELIMITER; 
```


















Scrivi il codice SQL per la creazione di un database che gestisca gli utenti di un sito web con aree riservate.Il database deve soddisfare i seguenti requisiti:  
- Memorizzare gli utenti registrati al sito.

Per ogni utente devono essere salvate almeno le seguenti informazioni: identificativo univoco, username, email, password (non in chiaro), data di registrazione, stato dell’account (attivo, sospeso, bannato)

Il sito prevede diverse aree, ad esempio:  
- area pubblica  
- area utenti registrati  
- area premium  
- area amministrazione

Ogni utente può avere accesso a una o più aree, in base ai permessi assegnati.

Auditing e controllo

Il database deve includere una tabella di auditing che registri automaticamente le modifiche ai dati degli utenti



```SQL

CREATE TABLE utenti(
	id INT AUTO_INCREMENT PRIMARY KEY,
	username VARCHAR(50) NOT NULL UNIQUE, 
	email VARCHAR(50),
	password CHAR(32) NOT NULL, 
	data_registrazione DATETIME, 
	stato_account VARCHAR(50)
);

CREATE TABLE aree(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	nome_area VARCHAR(50)
);

CREATE TABLE utenti_aree(
	id INT AUTO_INCREMENT PRIMARY KEY,
	id_utente INT,
	id_area INT,
	FOREIGN KEY (id_utente) REFERENCES utenti(id),
	FOREIGN KEY (id_area) REFERENCES aree(id)
);

CREATE TABLE audit_utenti(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	old_username VARCHAR(50) NOT NULL, 
	new_username VARCHAR(50) NOT NULL, 
	old_email VARCHAR(50), 
	new_email VARCHAR(50), 
	old_password CHAR(32), 
	new_password CHAR(32), 
	old_stato VARCHAR(50), 
	new_stato VARCHAR(50),
	operazione VARCHAR(50),
	eseguito_da VARCHAR(50)
);

DELIMITER // 

CREATE TRIGGER tgr_utenti
AFTER UPDATE ON utenti 
FOR EACH ROW 
BEGIN
INSERT INTO audit_utenti(
	old_username,
	new_username,
	old_email, 
	new_email, 
	old_password, 
	new_password, 
	old_stato, 
	new_stato,
	operazione,
	eseguito_da
)VALUES(
	OLD.username,
	NEW.username,
	OLD.email,
	NEW.email,
	OLD.password,
	NEW.password,
	OLD.stato_account,
	NEW.stato_account,
	"UPDATE UTENTE",
	USER()
);

END // 

DELIMITER ; 
```
























