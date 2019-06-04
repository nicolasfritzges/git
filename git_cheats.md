# Git Manual de Bolsillo

[<img src="https://github.com/aledc7/PHP-Certification/blob/master/aledc-logo.png?raw=true">](https://aledc.com)


Consultar el status del proyecto, esto nos mostrará información de en qué estado se encuentran nuestros archivos.
```js
git status
```

Añadir archivos al escenario (stage), se podría decir que es como tomarle una fotografía a este archivo, tal y como se encuentra en ese momento.

# Añadir un solo archivo
git add nombre_del_archivo

# Añadir todo en el directorio actual
git add --all
# O bien
git add .
1
2
3
4
5
6
7
# Añadir un solo archivo
git add nombre_del_archivo
 
# Añadir todo en el directorio actual
git add --all
# O bien
git add .
Mostrar diferencias, con esto podemos ver como se encuentra nuestro archivo cuando estaba consolidad en comparación a como lo tenemos actualmente.

git diff
1
git diff
Mostrar el historial, en ocasiones vamos a querer ver todas las consolidaciones (commits) que tengamos en nuestro historial.

git log
1
git log
En ocasiones va a ser necesario que eliminemos un commit, ya sea porque hicimos un commit y queremos volver a como estábamos anteriormente lo cual podemos hacerlo de la siguiente manera

# Soft reset dejará todo lo que tenía nuestro último commit en stage
git reset --soft IDENTIFICADOR_DEL_COMMIT

# Hard reset eliminará el commit junto con todos sus cambios
# y no podrán ser accesibles de nuevo
git reset --hard IDENTIFICADOR_DEL_COMMIT
1
2
3
4
5
6
# Soft reset dejará todo lo que tenía nuestro último commit en stage
git reset --soft IDENTIFICADOR_DEL_COMMIT
 
# Hard reset eliminará el commit junto con todos sus cambios
# y no podrán ser accesibles de nuevo
git reset --hard IDENTIFICADOR_DEL_COMMIT
NOTA: Es muy importante que si van a hacer algún reset lo hagan antes de enviar los cambios al repositorio remoto, lo cuál veremos en el siguiente video.
