# Primeros pasos en Linux

En primer lugar, familiarízate con la interfaz. Como puedes observar, no difiere demasiado de las interfaces de Windows o Mac. Puedes ver el escritorio, muy similar a los que ya conoces. Ubuntu también tiene un gestor de archivos (llamado Nautilus) bastante parecido a otros. A la izquierda, se despliega la barra de tareas. Puedes personalizar su posición. 

Prueba a clicar en el símbolo de los nueve cuadraditos del inferior de la barra de tareas. Verás que se despliegan las aplicaciones instaladas en el sistema (más similar a un smartphone quizás, pero nada extraño). Eso si, la suite de Microsoft Office no funciona en Ubuntu, así que tendrás que acostumbrarte a usar LibreOffice o las herramientas de Microsoft en navegador.

# La terminal
La terminal no es una característica exclusiva de Ubuntu, ni siquiera de Linux. Tanto MacOS como Windows tienen sus propias terminales. De hecho, como MacOS se basa en una arquitectura similar a Linux, muchos de los comandos que verás en este curso pueden aplicarse también. En el caso de Windows, difieren más, aunque las últimas versiones tienen la opción de activar un Subsistema Linux que ofrece una terminal idéntica a la de Linux. Revisar esta cuestión queda fuera del alcance de este curso.

Dicho esto, en MacOS o en Windows seguramente nunca hayas tenido que recurrir a la terminal/consola. Esto se debe a que son sistemas operativos diseñados para usuarios comunes, por lo que no es necesario recurrir a ella salvo para usos avanzados. Actualmente Ubuntu ha minimizado mucho el uso de su terminal, por lo que ya no es tan necesario como antes. Pero en NGS no vamos a ser usuarios comunes, así que tenemos que familiarizarnos con ella.

Explicado rápidamente, la terminal es un programa particular que nos permite **hablar** con el sistema operativo lo que permite ejecutar todo tipo de funciones avanzadas.

Para encontrar la terminal, ve a la bóveda de aplicaciones y busca un logo similar a este:

<img src="https://www.linuxadictos.com/wp-content/uploads/prompt.jpg" width="80">

Tras ejecutarlo, verás la pantalla del terminal. Te recomiendo que lo añadas a favoritos (en la barra de tareas, sobre el icono de la terminal, click derecho -> añadir a favoritos) para tenerla siempre a mano.

La pantalla del terminal es algo así:

<img src="https://www.solvetic.com/uploads/monthly_08_2017/tutorials-9832-0-85086400-1502272888.png">

**(Aviso: Los colores pueden cambiar)**

Lo que se ve en verde es el nombre del usuario y el nombre del host (del equipo vamos): nombre_de_usuario@nombre_de_host.

A continuación de los dos puntos, la terminal nos indica el **directorio** (la carpeta) en la que nos encontramos. El símbolo de la virgulilla ~ representa al directorio /home/. A continuación del directorio, tenemos el símbolo del dólar. A partir de este símbolo es que podemos escribir nuestras órdenes.

A esta parte de la terminal se le conoce como prompt

## Navegando con la terminal

Vamos a aprender nuestros primeros comandos. El comando **ls** (acrónimo de list) nos muestra una *lista* de los elementos presentes en nuestra carpeta. Prueba a escribirlo
```
ls
```
Deberías ver impresos en la terminal los nombres de los archivos y carpetas de tu directorio.

A continuación, vamos a movernos. Para ello, utilizamos el comando **cd** (change directory). Al comando cd hay que pasarle un *argumento*, es decir, un parámetro para que sepa lo que tiene que hacer. En este caso, el argumento es la ruta (path) hacia la que queremos movernos. Vamos a ir hacia Documentos

**Nota: Para que este comando funcione debes estar en el home. Además, los nombres de las carpetas pueden variar según tengas el sistema configurado en inglés, español u otro idioma**
```
cd Documents/
```

Ahora ya deberías estar en documentos, y la ruta impresa en el prompt debería haber cambiado. Si algo no ha ido bien, Ubuntu te lo dirá en la terminal. Es importante leer los mensajes que da el sistema, para saber si algún comando ha tenido problemas.

Hay un par de cuestiones que debes saber. Cuando utilizamos herramientas que manejen rutas, el punto (.) significa el directorio *actual*. Por ejemplo, si en nuestra carpeta actual tenemos un archivo llamado texto.txt, su ruta puede representarse como ./texto.txt. Por otra parte, el doble punto (..) representa el directorio inmediatamente *superior*. Eso podemos usarlo para ir directamente a otra carpeta que cuelga de la carpeta superior. Por ejemplo, si desde Documentos queremos ir directamente a Descargas, escribiremos:

```
cd ../Downloads
```

Y ya estamos en descargas.

Acuerdáte que la virgulilla representa el directorio Home, por lo que puedes utilizarlo para navegar rápidamente hacia carpetas que cuelguen de dicho directorio. Por cierto, la virgulilla la obtienes con Alt Gr + 4. Por tanto, una forma de volver a documentos es:

```
cd ~/Documents
```

# Creando carpetas y archivos

Desde la terminal también puedes crear carpetas. Te recomiendo que a la par de la terminal, abras el navegador de archivos y vayas hacia la carpeta Documentos para ver como se producen los cambios en tiempo real.

Considerando que estás en Documentos (y si no lo estás, navega hacia allí), vamos a usar el comando **mkdir** (make directory) para crear una carpeta propia. En el siguiente comando, sustituye mi_nombre por tu nombre.

```
mkdir mi_nombre
```

Ahora ya tienes una carpeta con tu nombre. Navega hacia allí.

```
cd mi_nombre
```

Con el comando touch puedes crear nuevos archivos vacíos. Prueba a crear un archivo de prueba:

```
touch prueba.txt
```

Si abres este archivo con Notepad u otra aplicación similar, verás que no contiene nada.

La terminal de Ubuntu tiene editores de texto integrados. Los más utilizados son vim y nano. Nosotros vamos a utilizar nano.
```
nano prueba.txt
```

Verás que la terminal ha cambiado de apariencia. Ahora es básicamente un bloc de notas. Prueba a escribir lo que quieras en el archivo y cuando termines, pulsa Ctrl + X. nano te preguntará si quieres guardar los cambios. Escribe Y para darle el ok. Ahora, si abres el archivo con Notepad verás que ha sido editado.

El comando **cat** (concatenar) muestra en pantalla el contenido del archivo que se le pasa como argumento (debe ser un archivo de texto):

```
cat prueba.txt
```

Aunque ahora esto no te parezca muy útil, más adelante veremos aplicaciones. 

Para borrar archivos, puedes utilizar el comando **rm** (remove):

```
rm prueba.txt
```

Y ya está borrado! Si quieres borrar directorio, puedes usar también rm, pero si el directorio tiene archivos, debes añadir el flag -r previamente:

```
rm -r directorio_a_borrar
```
**Cuidado: esto eliminará todo el contenido de la carpeta y de sus subcarpetas**

Pero ¿Que es esto de los flags? Avanza hacia la siguiente sesión para entenderlo:

- [Uso de flags]( https://github.com/ibloise/cursoLinux/blob/fd9cc7e8bcd3fd7685426ebb22734a82956d8657/flags.md](https://github.com/ibloise/cursoLinux/blob/main/flags.md )
