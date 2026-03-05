[[Bash e Shell]]

Quando siamo in bash noi possiamo utilizzare l'array. 

`array=(1 2 3 4 5 6 7 8)

e possiamo andare a cambiare i valori 

`array[0]=pippo`

possiamo manipolare il tutto con: 

```bash
${array[@:1]} # stampa dalla prima cella
${array[@:1:2]} # stampa cella 2 e 3
```
