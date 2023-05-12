# Fases de Traduccion

*Opciones para inicio de las fases de traduccion*

* Preprocesamiento: gcc -E NombreArchivo.c -o NombreArchivo.i
* Compilacion: gcc -S NombreArchivo.c -o NombreArchivo.s
* Ensamblado: gcc -c NombreArchivo.c -o NombreArchivo.o
* Vinculacion: gcc NombreArchivo.c -o NombreArchivo


1)Preprocesador
comando ejecutado : gcc -E hello2.c -o hello2.i
-La primer parte de codigo seria la libreria expandida y en el codigo creado el comentario lo reemplazo por un espacio
- int printf(const char * restrict s, ...) , esta funcion genera texto con formato bnajo el control del formato s y cualquier argumento adicional. Cada caracter generado se escribe en la secuencia stdout (puntero al objeto que controla el flujo standar de salida), devuelve los caracteres generado o un valor negativo si hay un error en la transmision
- 4 lineas de coidgo mas

2)Compilacion

