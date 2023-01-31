# Uso de flags

Se conocen como flags a diferentes argumentos que pueden pasarse a los programas de la terminal.

Estos argumentos/parámetros se indican con guiones siguiendo algunas convenciones:

Los flag de un guión solo llevan una letra:

```
ls -l
```
Los flags de un guión pueden pasarse juntos:

```
ls -l -h
```
es lo mismo que:

```
ls -lh
```

Los argumentos que tienen más de una letra se indican con doble guión:

```
ls --help
```

Estos flags no pueden combinarse.

## Ayuda

Para conocer los posibles argumentos que admite un programa de la terminal, habitualmente existe una documentación de ayuda. A esta documentación se accede o bien con el flag -h, con el flag --help o bien con los dos.

El argumento de ayuda imprimirá en pantalla el uso del programa, sus posibles argumentos, y cualquier información que el desarrollador haya considerado importante.

# Tipos de argumentos

Algunos argumentos son **lógicos** es decir, indicarlo cambia en si mismo el comportamiento del programa (como ya hemos visto, el flag -l cambia la manera en que ls nos muestra los archivos) mientras que otros requieren recibir **parámetros** a su vez (por ejemplo, el nombre de un archivo).


