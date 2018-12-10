# git - Uso y Comandos Básicos

- [x] AleDC

#### Este documento lista los comandos mas utilizados en git




- Mostrar usuario logueado
```
git config --global -l
```

- realizar un login desde la terminal
```
git config --global user.name "aledc7"
git config --global user.email "aledc@gmail.com"
```

- Para desloguearse
```
git config --global --unset user.name
git config --global --unset user.email
```

- para controlar una carpeta con git, se debe correr este comando por única vez
```
git init
```

- Este comando muestra en rojo los archivos que no está controlando, y en verde mostrará los que sí controla
```
git status
```

- vincular repo local con repo en github
```
git remote add origin https://github.com/aledc7/vueJS-2.git
git push -u origin master
```



- Agregar todos los archivos en rojo que no se estén controloando dentro de una carpeta.
- En vez del . se puede especificar un archivo particular en caso de que no se quiera agregar toda la carpeta.
```
git add .
```

- Confirma los cambios que se realizaron a los archivos, y se graba un mensaje para ese commit en particular.
```
git commit -m  "texto del commit"
```

- Descartar todos los cambios realizados (en caso de que no se quiera modificar nada)

```
git checkout -- .
```

- Descartar cámbios solo en un archivo específico


```
git checkout -- archivo_a_descartar_cambios.php
```


- mostrar los últimos cámbios, literalmente muestra el código de lo que se haya cambiado.
```
git diff
```

- muestra todos los commits que se hayan realizado.
```
git log
```

- similar a git log pero mucho mas completo, este es el que hay que utilizar.
```
git reflog
```

- excluye un archivo o una carpeta del control de git (los volverá a mostrar en rojo al hacer "git status")
```
git reset nombre_archivo.css
```


- este no hace falta explicarlo
```
git help
```

- Es posible crear 'alias'  que reemplacen largos comandos, de esta manera se logra escribir menos.
```
git config --global alias.nombre "comando_git_para_ese_alias"

aqui un ejemplo real que crea un alias llamado 'cabecera' para ver en que rama nos encontramos,
el comando original es el que se encuentra entre comillas. Aquí el ejemplo completo:

git config --global alias.cabecera "log --oneline --decorate --all --graph"

```

- listar todos los alias que se hayan creado, como el que se hizo arriba. 
  Puede que existan alias creados predeterminadamente.
```
git config --get-regexp alias
```

- dejar registrado un cámbio de nombre a algún archivo
```
git mv nombre_viejo.js  nombre_nuevo.js
```

- cambiar el texto que se le dió al último commit
```
git commit --amend -m  "nuevo texto del commit"
```

- borra archivos
```
git rm
```

- hacer un viaje en el tiempo hasta un commit específico, todo el código será reemplazado por el del commit indicado.
```
git reset --hard e37db00
```

- agregar una nueva rama
```
git branch  nombre_rama
```

- listar todas las ramas y saber cual tiene el HEAD
```
git log --oneline --decorate --all --graph
```

- pasar el head a otra rama
```
git checkout nombre_rama
```

- unificar la rama indicada a la rama actual en la que se encuentre el HEAD
```
git merge nombre_rama
```

- borrar una rama (irreversible)
```
git branch -d nombre_rama
```

- crea una etiqueta para la rama en la que se encuentre el HEAD
```
git tag nombre_etiqueta
```

- borra la etiqueta que se haya creado
```
git tag -d
```


- es posible poner una etiqueta a un commit existente, se debe indicar la version de ese commit, luego el id del commit, y por último el mensaje de la etiqueta.
```
git tag -a  v2.0.1 c62704e    -m "memsaje que quiera poner"
```

- con este comando mostraría el commit que he creado arriba.
```
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


- clonar un repositorio
```
git clone https://github.....ruta completa
```




