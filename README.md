# Git - Control de Versiones 
## Uso y Comandos Básicos

[![aledc.com](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/aledc.com.svg)](https://aledc.com)
[![License](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/mit-license.svg)](https://aledc.com)
[![GitHub release](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/release.svg)](https://aledc.com)
[![Dependencies](https://github.com/aledc7/Scrum-Certification/blob/master/recursos/dependencias-none.svg)](https://aledc.com)


- [x] AleDC

#### Este documento lista los comandos mas utilizados en git




- Mostrar usuario logueado
```php
git config --global -l
```

- Realizar un login desde la terminal
```php
git config --global user.name "aledc7"
git config --global user.email "aledc@gmail.com"
```

- Guardar las credenciales de git localmente

```php
git config --global credential.helper store
```




- Para desloguearse
```php
git config --global --unset user.name
git config --global --unset user.email
```

- Para controlar una carpeta con git, se debe correr este comando por única vez
```php
git init
```

- Este comando muestra en rojo los archivos que no está controlando, y en verde mostrará los que sí controla
```php
git status
```



- Vincular repo local con repo en github.
```php
git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:aledc7/nombre-repo.git

// Hacer un pull de lo actual antes de hacer un push
git pull origin master

// en caso de que tire un error de urelated agregarle este parámetro.
git pull origin master --allow-unrelated-histories

// Finalmente hacemos el push
git push -u origin master
```


# Ignorar Archivos Untracked (en Rojo) con -n primero se observa lo que se va a borrar
```php
git clean -n
```

Then when you are comfortable (because it will delete the files for real!) use the -f option:

Luego con el -f se ejecuta la opcion y se descartan los cambios hechos en los archivos en rojo.
```php
git clean -f
````

Here are some more options for you to delete directories, files, ignored and non-ignored files

To remove directories, run:

```php
git clean -fd
````

To remove ignored files, run 
```php
git clean -fX
````

To remove ignored and non-ignored files, run
```php
git clean -fx
````

Note the case difference on the X for the two latter commands.





- Agregar todos los archivos en rojo que no se estén controloando dentro de una carpeta.
- En vez del . se puede especificar un archivo particular en caso de que no se quiera agregar toda la carpeta.
```php
git add .
```

- Confirma los cambios que se realizaron a los archivos, y se graba un mensaje para ese commit en particular.
```php
git commit -m  "texto del commit"
```

- Descartar todos los cambios realizados (en caso de que no se quiera modificar nada)

```php
git checkout -- .
```

- Descartar cámbios solo en un archivo específico


```php
git checkout -- archivo_a_descartar_cambios.php
```


- Mostrar los últimos cámbios, literalmente muestra el código de lo que se haya cambiado.
```php
git diff
```

- Muestra todos los commits que se hayan realizado.
```php
git log
```

- Similar a git log pero mucho mas completo, este es el que hay que utilizar.
```php
git reflog
```

- Excluye un archivo o una carpeta del control de git (los volverá a mostrar en rojo al hacer "git status")
```php
git reset nombre_archivo.css
```


- Este no hace falta explicarlo
```php
git help
```

- Es posible crear 'alias'  que reemplacen largos comandos, de esta manera se logra escribir menos.
```php
git config --global alias.nombre "comando_git_para_ese_alias"

aqui un ejemplo real que crea un alias llamado 'cabecera' para ver en que rama nos encontramos,
el comando original es el que se encuentra entre comillas. Aquí el ejemplo completo:

git config --global alias.cabecera "log --oneline --decorate --all --graph"

```

- Listar todos los alias que se hayan creado, como el que se hizo arriba. 
  Puede que existan alias creados predeterminadamente.
```php
git config --get-regexp alias
```

- Dejar registrado un cámbio de nombre a algún archivo
```php
git mv nombre_viejo.js  nombre_nuevo.js
```

- Cambiar el texto que se le dió al último commit
```php
git commit --amend -m  "nuevo texto del commit"
```

- Borra archivos
```php
git rm
```

- Hacer un RESET hasta un commit específico, todo el código será reemplazado por el del commit indicado.
```php
git reset --hard e37db00
```

- Agregar una nueva rama
```php
git branch  nombre_rama
```

- Listar todas las ramas y saber cual tiene el HEAD

```php
git branch -a

```

- Pasar el head a otra rama
```php
git checkout nombre_rama
```

- Unificar la rama indicada a la rama actual en la que se encuentre el HEAD
```php
git merge nombre_rama
```

- Borrar una rama (irreversible)
```php
git branch -d nombre_rama
```

- Crea una etiqueta para la rama en la que se encuentre el HEAD
```php
git tag nombre_etiqueta
```

- Borra la etiqueta que se haya creado
```php
git tag -d
```


- Es posible poner una etiqueta a un commit existente, se debe indicar la version de ese commit, luego el id del commit, y por último el mensaje de la etiqueta.
```php
git tag -a  v2.0.1 c62704e    -m "memsaje que quiera poner"
```

- Con este comando mostraría el commit que he creado arriba.
```php
git show v2.0.0.1
```
____________________________________________________________________________________________________________

###### Asociar carpeta local con github

1) Loguearse en la web de github y crear un nuevo repositorio
2) Localmente en la terminal, ir a la carpeta que se quiere subir al repo creado en el paso 1
3) git init
4) git add .
5) git commit -m "primer commit"
6) git remote add origin https://github.com/aledc7/nombre_repo.git
7) git push -u origin master (pedirá user y pass)

Con estos pasos se empieza a controlar una carpeta local con git.


- Clonar un repositorio
```php
git clone https://github.....ruta completa
```


###### Git Ignore

Para que Git ignore archivos o carpetas que le indiquemos, estos deben estar declarados en el archivo llamado __.gitignore__

Pero si el archivo ya fue agregado previamente, es posible que GIT no ignore estos archivos, incluso estando declarado en el git ignore.  
Para solucionar esto, es necesario borrar estos archivos del cache de git.

Este comando borrará un archivo especifico del cache de git, de esta manera git dejará de controlar el archivo indicado.
```js
git rm -r --cached nombre_archivo.js
```

Si queremos borrar el cache completo: 
```js
git rm -r --cached .
```

luego de este paso, será necesario agregar nuevamente a git los archivos de nuestro proyecto con este comando:

```js
git add . 
```
Finalmente hacemos un commit para guardar todos estos cambios.
```js
git commit -m "Ahora si git ignorará todos los archivos de mi gitignore"
```

### Automatizando un Commit y Push

Script para automatizar todo el proceso de un push, agregando primero los archivos con add, luego haciendo el commit, y finalmente el push a la rama master.   
Para crear este script, primero es necesario saber en que carpeta del servidor linux se encuentra git.  
Esto puede saberse con este commando:   
```php
whereis git
````

Una vez que tengo este dato, ya me es posible crear el script de autopush.

Este es un ejemplo completo y funcional de un script de autopush

```php
#!/bin/bash
# Automatizando el commit y push

# Agrego a git todos los archivos nuevos con extension .gz
cd /home/aledc/software/systems && /usr/bin/git add *.gz

# commit automatico de la carpeta backups
cd /home/aledc/software/systems && /usr/bin/git commit -m "push automatico de los archivos *.gz de la carpeta backups del sistema"

# push automatico del commit anterior
cd /home/aledc/software/systems && /usr/bin/git push origin master
````



