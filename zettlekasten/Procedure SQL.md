Le procedure [[Structured Query Language (SQL)]] sono un modo più sicuro di eseguire [[Funzioni in SQL]]. Queste infatti sono molto più sicure.

CREATE PROCEDURE login(
	IN u VARCHAR(50),
	IN p VARCHAR(50)
)
BEGIN
	SELECT  FROM users  WHERE username=u AND password=p;
END; 

DELIMITER // 

CREATE PROCEDURE login_user(
	IN u VARCHAR(50),
	IN p VARCHAR(50)
)
BEGIN 
	a=SELECT id FROM users WHERE username=u AND password=p,
	INSERT INTO log_accessi(user_id, data_accesso) VALUES (a, current-date),
	SELECT id, role FROM users WHERE username=u AND password=p; 
