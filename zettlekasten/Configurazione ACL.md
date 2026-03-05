[[Access controls list (ACL)]],   [[Processo configurazione network]] 

- Andiamo al R2
	- Ip access-list extended REGOLE_BASE
	- deny icmp any 10.0.0.0 0.255.255.255 echo 
	- permit ip any any 
- Ora andiamo ad aggiungere una riga in mezzo 
	- ip access-list extended REGOLE_BASE
	- 15 deny tcp host 192.168.0.1 host 10.0.0.101 eq www