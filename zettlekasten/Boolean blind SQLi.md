questo è un metodo di [[SQL Injection]] ma è [[Blind SQL injection]]. Questo funziona attraverso il Boolean. 

Qui possiamo anche usare time-based blind (mysql/mariadb)

1 AND IF (SUBSTRING(user(),1,1)="r", SLEEP(5), 0)-- 