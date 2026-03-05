[[Query]]  e [[Trigger]]

``` SQL
DELIMITER $$
CREATE TRIGGER log_update_portafoglio
AFTER UPDATE ON portafoglio
FOR EACH ROW
BEGIN
    INSERT INTO audit_portafoglio (
        portafoglio_id,
        nome,
        cognome,
        saldo_precedente,
        saldo_nuovo,
        operazione,
        eseguito_da
   )
    VALUES ( 
	    OLD.id,
        OLD.nome,
        OLD.cognome,
        OLD.saldo,            
        NEW.saldo, 
        'UPDATE SALDO',
        USER()        
    );
END $$
DELIMITER ;
```
