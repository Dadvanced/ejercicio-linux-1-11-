# Ejercicios de Linux
Ejercicios de la consola de Linux

## Ejercicio 1
- Muestra todas las fotos *.jpg* en el directorio actual.



```console
ls *.jpg
```

## Ejercicio 2
- Muestra todos los archivos del directorio */usr/bin* que empiecen con la letra “j”.



```console
ls /usr/bin/j*
```

## Ejercicio 3
- Muestra todos los archivos en el directorio */usr/bin* que empiecen por la letra “k”, con una “a” en tercer lugar.*


```console
ls /usr/bin/k?a*
```

## Ejercicio 4
- Muestra todos los archivos en el directorio */bin* que terminen en  “n”.



```console
ls /bin/*n
```

## Ejercicio 5
- Muestra todos los archivos en el directorio */etc* y todos los archivos en cada directorio recursivamente.



```console
ls -R /etc/
```

## Ejercicio 6
- En tu directorio home crea otro directorio llamado *test*.copia el archivo *gzip* del directorio */bin* a *test*. Crea un duplicado de *gzip* llamado *gzip2* dentro de *test*.

	- Creamos el directorio *test* en el directorio *home*.

```console
mkdir test
```

	- Luego copiamos el archivo *gzip* desde el directorio */bin* al directorio *test*.

```console
cp /bin/gzip test/
```

	- Y para duplicarlo dentro de *test/* escribimos:
	
```console
cp test/gzip test/gzip2
```

## Ejercicio 7
- Cambia el nombre del directorio *test* a *test2*. Crea *test3* en el mismo nivel del árbol de directorio de *test2* y mueve todos los arhicvos de *test2* a *test3*. Borra *test2*.

	- Cambiamos el nombre del directorio *test* a *test2* con el siguiente comando.

```console
mv test/ test2/
```

	- Creamos el directorio *test3* en el mismo nivel que *test2* y movemos todos los archivos de *test2* a *test3*.

```console
mkdir test3/
mv test2/* test3/
```

	- Ahora borramos *test2*.

```console
rmdir test2/
```

## Ejercicio 8
- Crea un archivo vacío llamado “*?Hello all?*”. ¿Puedes? ¿Es buena idea nombrar así a un archivo? Explica tu respuesta.

	- Se puede crear, pero se crean 2 archivos por separado, además no es una buena idea nombrar de esta forma a los archivos, ya que "*" y "?", son ejemplos de comodines y se usan para relacionar caracteres con otras combinaciones de caracteres, ya sea de forma múltiple o individual. Su empleo más común es abarcar un número más amplio de archivos o directorios.


## Ejercicio 9
- Crea un directorio llamado *multimedia_test* y copia todo el contenido del directorio *multimedia* en él. Luego, crea 2 archivos en *multimedia/video/*, uno que se llame *films.txt* y otro llamado *actors.txt*. Edita el archivo *films.txt* y escribe el título de tu película favorita. Luego, crea otro archivo en *multimedia_test/video/*, que tambien se llame *films.txt*. Edita éste archivo y ahora escribe los títulos de tus cinco películas favoritas. Copia todo el contenido de *multimedia* a *multimedia_test* asegurando que solo las versioens de los archivos modificadas recientementen quedan. Para comprobar que todo está bien, comprueba si *multimedia_test/video* contiene el archivo vacío *actors.txt* y el archivo *films.txt* contiene 5 títulos y no 1.

	- Creamos un directorio llamado *multimedia_test/* y copiamos todo el contenido desde el directorio *multimedia/* dentro de él.

```console
mkdir multimedia_test/
cp -R multimedia/* multimedia_test/
```

	- Ahora creamos los dos archivos *films.txt* y *actors.txt* en el directorio *multimedia/video/* y editamos el archivo *films.txt/*.

```console
cd multimedia/video/
touch films.txt actors.txt
mcedit films.txt
```

	- Ahora creamos otro archivo en el directorio *multimedia_test/video/*, también llamado *films.txt* y escribimos los 5 títulos de nuestras películas favoritas.

```console
cd ../..
cd multimedia_test/video/
touch films.txt
mcedit films.txt
```

	- Ahora copiamos todo el contenido del directorio *multimedia/* dentro del directorio *multimedia_test/*, asegurándonos de que no se copien los archivos que estén más desactualizados que los de la ruta destino.

```console
cd ../.. 
cp -R -u multimedia/* multimedia_test/
```

	- Por último comprobamos si el archivo *films.txt* del directorio *multimedia_test/* tiene nuestras 5 películas favoritas y no 1.
	
¨¨¨console
cd multimedia_test/video/
cat films.txt
¨¨¨

## Ejercicio 10
- Borra el directorio *multimedia/pictures/others*. El sistema debe preguntar por confirmación.



```console
rmdir multimedia/pictures/other
```

	- El sistema no preguntó confirmación.

## Ejercicio 11
- Mueve el archivo *films.txt* que está en *multimedia/video*, al directorio superior, a la vez que renombras el archivo a * my_films.txt*.



```console
mv multimedia/video/films.txt multimedia/my_films.txt
```


# Ejercicios de Linux - Tema 4

## Ejercicio 1
- Completa la siguiente tabla:

| 654 | rw-r-xr-- |
|:-----:|:-----------:|
| 766 | rwxrw-rw- |
| 777 | rwxrwxrwx |
| 520 | r-x-w---- |
| 764 | rwxrw-r-- |
| 440 | r--r----- |



## Ejercicio 2
- Crea el grupo *office1* y *office2*

```console
sudo groupadd office1
sudo groupadd office2
```

## Ejercicio 3
- Crea el usuario *gearoid* y *paul*. Esos usuarios deben pertecener sólo al grupo *office1*.

```console
adduser georid --ingroup office1
adduser paul --ingroup office1
```


