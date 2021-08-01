# DevOps-Fundamentos-y-herramientas
## Curso EDX AnahuacX - UAMY.CP6.1x + lecciones en webminal.org

Terminal / bash

promt://

comando `ls` como listar, para encontrar objetos en el sistema de archivos / contenido del directorio
  -R recursivo (muetra todo)
  -C -b es dir
  
`clear` limpia pantalla

`echo` muestra el mensaje entre comillas " " 
`echo` "hello" > hello.txt  agrega palabra hello al archivo >> agrega renglon abajo

`cat` muestra archivo llamado x ej cat hello.txt
`head` -2 muestra solo las dos primeras lineas
`tail` -2 muestra solo las dos ultimas lineas
 
`stat` muestra info imporante del archivo

comando `pwd` para mostrar dir actual, pridunt working directory

comand `man` muestra manual para comando especefico

`man -k TEXT` busca titulos y synopsis con TEXT

`man chown` muestra el manual para el comando chown

man tiene 8 seciones
- 1 comandos de usuario
- 2 llamadas de sistema
- 3 libreria de referencia
- 4 controladores de dispositivos
- 5 archivos de configuracion
- 6 juegos
- 7 miscelaion ascii map o operador c
- 8 comando de systema

`cd` acceder de directorio, solo es home
  .. abajo
  - vuelve
 
 `cp` copia
 `mv` mueve
 
 `ln` crea vinculo

`touch` con archivo que no existe lo crea, cuando ya existe actuliza los valores de ultima modificacion y acceso

`mkdir` crea directorio

`mkdir` -vp dir2/dir/3/dir4 crea varios directorios
  -p crea directorio padre

`rm` remover archivo
`rmdir` remover directorio

`du` muestra uso de disco 
  -h legible por humano
  moñito es home

`md5sum` checksum

`ps` muestra procesos corriendo

`kill` mata proceso por id
  -9 cuando ta duro de matar
  
  `killall` mata todos por nombre
    -u mata por usuario
    -w espera al procesop por morir
    
`pidof` muestra el id de un proceso

`nice` ejecuta bun programa con la prioridad modificada -20 a 19 
    
`renice` modifica la prioridad

`top` muestra una vista dinamica en tiempo real del sistema 

`pstree` arbol de procesos

`time` muestra esstadisticas de el programa que ejecuta


### permisos

rbac rol base acceso control

lectura r
escritura w
ejecucion x

primera tripleta permisos que aplicanl al dueño del objeto
segunda trupoleta permisos que aplucan al grupo que pertenece el dueño
tercera tripleta permisos que aplican a todos los demas

`chhown` cambia usuario:grupo nombredearchivo
   -R recursivo al arbol de dir
   -h no siga los cambios simbolicos, cambia ellink y no el archivo objetivo
   -f muestre no error

Examples:
Root changes the ownership of "/etc/passwd" and "/etc/shadow" to user root, group wheel:

 # `chown root:wheel /etc/passwd /etc/shadow`
The same, but only changing the owner:

 # `chown root: /etc/{passwd,shadow}`
The same, but only changing the group:

 # `chown :wheel /etc/{passwd,shadow}`
Root gives every file in "/etc/ssh", including files in subdirectories, to user root, group wheel:

 # `chown -R root:wheel /etc/ssh`
The same, but excluding files in directories (and the invisible files "/etc/ssh/.*" will also be missed):

 # `chown root:wheel /etc/ssh/*`
User "tux" changes the directory "/usr/local/src/xc" from group "tux" to group "wheel". Tux is a member of both groups.

 $ ls -ld /usr/local/src/xc
drwxr-xr-x  11 tux  tux  512 Sep 30 16:19 /usr/local/src/xc
$ chown tux:wheel /usr/local/src/xc
$ ls -ld /usr/local/src/xc
drwxr-xr-x  11 tux  wheel  512 Sep 30 16:19 /usr/lo


`chmod` modificacion binaria de permisos
  u usuario
  g grupo
  + agrega
  - quita
  = esta
