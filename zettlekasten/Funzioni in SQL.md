[[Query]]

Ci sono funzioni che sono già pronte come per esempio: 
- SELECT nome, UPPER(nome) from persona;
- SELECT CONCAT (nome,' ',cognome) FROM persona;

Per creare una funzione noi possiamo andare ad usare

- DELIMITER //
- CREATE FUNCTION nome_funzione(parametro TIPO)
- RETURS TIPO_RITORNO
- DETERMINISTIC 
- BEGIN
- -- istruzioni
	- RETURN valore; \
- END //

- DELIMITER ; 

Esempio 
- DELIMITER //
- CREATE FUNCTION somma(a INT, b INT)
- RETURNS INT
- DETERMINISTIC 
- BEGIN
- -- istruzioni
	- RETURN a+b ; 
- END //

- DELIMITER ; 

DELIMITER //
CREATE FUNCTION duplicato(u VARCHAR(50), p VARCHAR(50))
RETURN INT
BEGIN
	RETURN (SELECT COUNT( * ) FROM users WHERE username=u AND password=p);
END //
DELIMITER:

------------ DROP -----------------
drop function nome_funzione;

------------ SOMMA -----------------
DELIMITER //

CREATE FUNCTION somma(a INT, b INT)
RETURNS INT
DETERMINISTIC
BEGIN
	RETURN a + b;
END //

DELIMITER ;

------------ DOPPIO -----------------

DELIMITER //

CREATE FUNCTION doppio(x INT)
RETURNS INT
DETERMINISTIC
BEGIN
	RETURN x * 2;
END //

DELIMITER ;

------------- ABSOLUTE ----------------

DELIMITER //

CREATE FUNCTION valore_assoluto(x INT)
RETURNS INT
DETERMINISTIC
BEGIN
	IF x < 0 THEN
		RETURN -x;
	ELSE
		RETURN x;
	END IF;
END //

DELIMITER ;

------------ PW DEBOLE ------------

DELIMITER //

CREATE FUNCTION password_debole(x VARCHAR(50))
RETURNS INT
DETERMINISTIC
BEGIN
	IF x='1234' OR x='password' THEN
		RETURN 5;
	ELSE
		RETURN 9;
	END IF;
END //

DELIMITER ;

------------ PW DEBOLE ------------

DELIMITER //

CREATE FUNCTION password_debole(x VARCHAR(50))
RETURNS VARCHAR(50)
DETERMINISTIC
BEGIN
	IF x='1234' OR x='password' THEN
		RETURN 'password debole';
	ELSE
		RETURN 'password forte';
	END IF;
END //

DELIMITER ;

------------ MEDIA ------------

DELIMITER //

CREATE FUNCTION media(voto FLOAT)
RETURNS FLOAT
DETERMINISTIC
BEGIN
	RETURN voto;
END //

DELIMITER ;


------------ TOTALE ------------

DELIMITER //

CREATE FUNCTION totale(u VARCHAR(50), p VARCHAR(50))
RETURNS INT
BEGIN
	RETURN (select COUNT(*) from credenziali where username=u AND password=p);
END //

DELIMITER ;

------------ PROCEDURA ---------

DELIMITER //
CREATE PROCEDURE login(
	IN u VARCHAR(50),
	IN p VARCHAR(50)
)
BEGIN
	SELECT id FROM credenziali WHERE username=u AND password=p;
END //

DELIMITER ;

LINK: 
[[Funzioni pericolose SQL]]

