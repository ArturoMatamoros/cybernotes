[[Bash e Shell]]
## Definizione 
le [[Bash e Shell]] expansions ci permettono di utilizzare [[Comandi filtri]] (come per esempio grep) per cercare quello di cui abbiamo bisogno facilmente.
le bash expansions fondamentali sono:
• Il testo non deve essere quotato nè con * nè con
• * matcha qualsiasi numero di ogni caratteri
• ? matcha un solo carattere
• ~ rappresenta la home directory:
• ~/file.txt equivale a /home/martino/file.txt sel'utente è martino
•. e .. non vengono espansi, sono propriamente parte di un path
• Liste racchiuse tra { ... } vengono espanse
• mkdir / tmp/{dir1, dir2} viene espanso in mkdir /tmp/dir1 /tmp/dir2