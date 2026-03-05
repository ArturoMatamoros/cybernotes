Questo è un [[Tipi di SQL injection]] che sfrutta: 
`SELECT * FROM products WHERE category = 'Gifts' AND released = 1`

Questa si trova tipicamente dove abbiamo url di tipo
`https://insecure-website.com/products?category=Gifts`


Dove la AND released ci fa capire che ci sono dati che sono nascosti. Per mostrare questi prodotti che teoricamente possono essere all'interno del database noi possiamo andare a rimuovere quest'ultima parte e mostrare tutto. Inseriamo quindi :
- `Gifts' -- ` 
	- Utilizzando il commento noi andiamo a eliminare la seconda parte
	- mostriamo quindi tutti i dati di quella categoria 
-  `Gifts' OR 1=1-- `
	- qui invece andiamo ad inserire tutti i dati all'interno di tutta la tabella 