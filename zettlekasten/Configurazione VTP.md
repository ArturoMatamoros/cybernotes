Configuriamo il [[VTP]]
1. Impostiamo il dominio VTP:
    vtp domain cisco
2. Impostiamo la modalità server (anche se è quella predefinita):
    vtp mode server
3. (Opzionale ma consigliato) Impostiamo la password VTP:
    vtp password cisco
- INSERIAMO UN NUOVO SWITCH
	- vtp mode client
	- interface g0/1
	- switchport mode trunk 
	- do sh interface trunk
- Ora andiamo a configurare le interfacce
	- Interface range fa0/1-15
	- switchport mode access
	- switchport access vlan 10