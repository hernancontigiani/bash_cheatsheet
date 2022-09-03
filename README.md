# bash_cheatsheet
Comandos útiles de bash

### Visualizar el consumo de espacio por carpetas
```sh
$ sudo du -sh *
```
Ordenado por tamaño de menor a mayor:
```sh
$ sudo du -sh * | sort -h
```
Ordenado por tamaño de mayor a menos:
```sh
$ sudo du -sh * | sort -rh
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
