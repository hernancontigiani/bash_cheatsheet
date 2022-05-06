# bash_cheatsheet
Comandos útiles de bash

### Visualizar el consumo de espacio por carpetas
```sh
$ sudo du -sh *
```

### Buscar archivos o contenido
Buscar por un archivo
```sh
$ find . -type f -name *nombre*
```
Buscar por un contenido en archivos
```sh
$ find . -type f | xargs grep -Hn "contenido"
```
