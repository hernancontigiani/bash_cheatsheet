# Bash Cheatsheet
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

### Liberar espacio de logs
Setear tamaño máximo de los logs
```
sudo journalctl --vacuum-size=50M
```
Limpiar todos los logs más viejos a 2 días
```
$ journalctl --vacuum-time=2d
```
Forzar la limpieza del syslog (de /var/log):\
https://stackoverflow.com/questions/35638219/ubuntu-large-syslog-and-kern-log-files
```
$ sudo su
$ > /var/log/syslog
$ systemctl restart syslog
```
Agregar a las configuraciones de logrotate max size:
- Editar archivo:
```
sudo nano /etc/logrotate.d/rsyslog
```
Agregar el parámetro maxsize:
```
/var/log/syslog
{
    rotate 7
    daily
    maxsize 1G # add this line
    missingok
    notifempty
    delaycompress
    compress
    postrotate
        /usr/lib/rsyslog/rsyslog-rotate
    endscript
}
```
