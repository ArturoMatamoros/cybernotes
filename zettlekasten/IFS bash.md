[[Bash e Shell]]

L'IFS è un array con al suo interno tutte le combinazioni di caratteri che separano le parole. Questi sono lo spazio, il tab e l'accapo. 

Noi possiamo andare a manipolare tutto questo in modo tale da avere un nostro separatore se necessario. 

``` bash
#!/bin/bash
# user lowercase possibly
# shell variables are uppercase!

#   \  = removes meaning next char
#   ''  = removes meaning of all the chars
#   ""  = removes menaing of all char except $

# Internal Field Separator
echo ${IFS}
# bash @Q =  quoted expansion
echo ${IFS@Q}
/bin/bash -c 'echo ${IFS@Q}'
# zsh internal field separators
echo -n "${(q)IFS}" | cat -A

echo "ciao${IFS[1]}come"
echo "ciao${IFS[2]}come"
echo "ciao${IFS[3]}come"

for (( i = 1; i <= ${#IFS}; i++ )); do printf "%q\n" "${IFS[i]}"; done

# create 5 files. Word splitting tramite IFS
numbers="1 2 3 4 5"
touch $numbers
# create 1 file
touch "$numbers"
# create 1 file
numbers="1,2,3,4,5"
touch $numbers

# create 5 files!
numbers="1,2,3,4,5"
IFS=","
touch $numbers


# per non "rompere "IFS"
    OLDIFS=$IFS
    IFS=","
    touch $numbers
    IFS=$OLDIFS
# oppure
    IFS=',' touch $numbers
```