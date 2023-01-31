# Manejo avanzado de archivos

Vamos a aprender a manejarnos con múltiples archivos. Para ello, lo primero que vamos a hacer es descargar unos pocos archivos fasta que tenemos disponibles en este repositorio. Puedes hacerlo manualmente, o bien aprovecharte de la terminal (necesitas internet, claro). 

Para descargarlo automáticamente, ejecuta los siguientes comandos. Debes hacerlo en la carpeta en la que quieres descargar los archivos:
```
fastas=(IonXpress_001.fasta IonXpress_002.fasta IonXpress_003.fasta IonXpress_004.fasta IonXpress_007.fasta)
for fasta in "${fastas[@]}";do
wget https://raw.githubusercontent.com/ibloise/cursoLinux/main/fastas/"$fasta"
done

#Para tener un par de archivos con los que probar los siguientes pasos, vamos a crear archivos de mentira:

touch emptyfile.txt
touch IonXpress_fake.txt
touch emptyfasta.fasta
```
No te preocupes por el comando, son usos más avanzados de la terminal.

Ahora que tenemos los fasta en la carpeta, vamos a aprender a trabajar archivos en bloque.

Para ello podemos usar el comodín (*). Vamos a hacer un par de pruebas:

```
# Con el comodín *.fasta, podemos acceder a todos los archivos con la extensión fasta del directorio:
ls *.fasta

#Con el comodín en IonXpress_* podemos acceder a todo lo que empiece por IonXpress_:

ls IonXpress_*

#Con IonXpress_*.fasta accedemos a todo lo que empieza por IonXpress_ y termina por .fasta

ls IonXpress_*.fasta

```

De esta manera, podemos realizar operaciones en masa sobre los archivos. 

El comando **mv** (move) aún no lo hemos visto. Sirve para mover archivos. Veámoslo:
```
#Creamos una carpeta para llevarnos los fastas

mkdir fastas

mv IonXpress_*.fasta fastas

ls fastas/ #Como ves, podemos listas directorios diferentes al activo
cd fastas
```

¿Te acuerdas del comando cat? Pues ahora vamos a utilizarlo en combinación con una instrucción que se conoce como **redirección de la salida** para crear un multifasta en un momento.

Con **>** mandamos las salidas de texto, que normalmente Ubuntu mostraría en pantalla, al archivo que especifiquemos. No es necesario que ese archivo exista.

```
#Vamos a utilizar cat solo:

cat *.fasta

#Como ves, esto no tiene mucho valor. Sin embargo:

cat *.fasta > multifasta.fasta

# Ahora mismo tenemos todos nuestros archivos fasta en un único multifasta!
```

