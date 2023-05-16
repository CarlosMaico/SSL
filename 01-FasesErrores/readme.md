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

comando ejecutado : gcc -S hello3.c -o hello3.s
resultado: 
hello3.c: In function 'main':
hello3.c:5:5: warning: implicit declaration of function 'prontf'; did you mean 'printf'? [-Wimplicit-function-declaration]
    5 |     prontf("La respuesta es %d\n");
      |     ^~~~~~
      |     printf
hello3.c:6:5: error: expected declaration or statement at end of input


- Lenguaje ensamblador, al realizar la etapa de compilacion se produce el codigo ensamblador, este codigo se obtuvo por hacer una baja de nivel, con objetivo de ser la entrada para la etapa de ensamblado

3)Vinculacion

codigo ejecutado : gcc hello5.c -o hello5
$ ./hello5.exe
La respuesta es 879895472
- trajo cualquier valor que este precargado en %d?? no se si esta bien

4)Correccion Bug

$ ./hello6.exe
La respuesta es 42

- se verifica

5)Remocion de Prototipo
comando ejecutado./hello7.exe
resultado: La respuesta es 42

- Funcion por que en el proceso de compilacion, en alguna etapa ya hace referencias a librerias???

6)Compilacion Separada: Contratos y Modulos

