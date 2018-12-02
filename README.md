# git - Comandos Básicos

#### Este documento lista los comandos mas utilizados en git




- Mostrar usuario logueado
```
git config --global -l
```

- para controlar una carpeta con git, se debe correr este comando por única vez
```
git init
```

- Este comando muestra en rojo los archivos que no está controlando, y en verde mostrará los que sí controla
```
git status
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


- mostrar los últimos cámbios, literalmente muestra el código de lo que se haya cambiado.
```
git diff
```

- 
```
git log
```

```
git reset
```

```
git help
```

```
git config --global alias.agregar "add ."
```


```
git config --get-regexp alias
```

```
git mv nombre_viejo.js  nombre_nuevo.js
```


```
git commit --amend -m  "nuevo texto del copmmit"
```

```
git rm
```


```
git reflog
```

```
git reset --hard e37db00
```


```
git branch  nombre_rama
```

```
git log --oneline --decorate --all --graph
```

```
git checkout nombre_rama
```


```
git merge nombre_rama
```

```
git branch -d nombre_rama
```

```
git tag
```

```
git tag -d
```

```
git tag -a  v.2.0.0 -m
```

```
git show v2.0.0.0
```



```
git config --global user.name "aledc7"
```

```
git config --global user.email "aledc@gmail.com"
```

```
git clone https://github.....
```




