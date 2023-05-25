# Fases de Traduccion

*Opciones para inicio de las fases de traduccion*

* Preprocesamiento: gcc -E NombreArchivo.c -o NombreArchivo.i
* Compilacion: gcc -S NombreArchivo.c -o NombreArchivo.s
* Ensamblado: gcc -c NombreArchivo.c -o NombreArchivo.o
* Vinculacion: gcc NombreArchivo.c -o NombreArchivo


1)Preprocesador

comando ejecutado : gcc -E hello2.c -o hello2.i

b) La primer parte de codigo seria la libreria expandida recurisvamente los archivos referenciados y en el codigo creado el comentario lo reemplazo por un espacio. Ahorra el trabajo de declarar funciones al programador. 

d) int printf(const char * restrict s, ...) , es una declaracion que acepta un argumento como minimo del tipo puntero a un char, el cual es el comienzo a una cadena la cual no va a poder modificar lo que apunta, este primer parametro es de entrada.

c) No expandio ninguna libreria, simplemente agrego un par de logeo, pero funcionalmente sigue estando igual.

2)Compilacion

a)
comando ejecutado : gcc -S hello3.c -o hello3.s

resultado: 
hello3.c: In function 'main':
hello3.c:5:5: warning: implicit declaration of function 'prontf'; did you mean 'printf'? [-Wimplicit-function-declaration]
    5 |     prontf("La respuesta es %d\n");
      |     ^~~~~~
      |     printf
hello3.c:6:5: error: expected declaration or statement at end of input

Aca aparecio un error en la etapa de compilacion ya que falta cerrar llaves del main.

c) Lenguaje ensamblador, al realizar la etapa de compilacion se produce el codigo ensamblador, este codigo se obtuvo por hacer una baja de nivel, con objetivo de ser la entrada para la etapa de ensamblado. Vemos en este legnuaje ensamblador que hay una llamada a prontf

d) Al momento de ensamblar generamos un archivo .o el cual permite realizar un analisis byte a byte ya que no es mas que un archivo de bytes. cada byte represetna una instruccion al microprocesador.

3)Vinculacion

a)codigo ejecutado : gcc hello4.o
C:/msys64/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/12.2.0/../../../../x86_64-w64-mingw32/bin/ld.exe: hello4.o:hello4.c:(.text+0x1f): undefined reference to 'prontf'collect2.exe: error: ld returned 1 exit status

Aca se ve que intento vinvular con la biblioteca estandar y que se intento referenciar a algo que no esta definido que es prontf, por lo tanto es un error de vinculacion

b) codigo ejecutado : gcc hello5.c -o hello5
$ ./hello5.exe
La respuesta es 291185584
c) trajo cualquier valor que no es el esperado, es un valor anterior que quedo en el stack que se interpreto como decimal

4)Correccion Bug

$ ./hello6.exe
La respuesta es 42

a) se verifica que funciona bien

5)Remocion de Prototipo
comando ejecutado./hello7.exe
resultado: La respuesta es 42

- Funcion por que en el proceso de compilacion, en alguna etapa ya hace referencias a librerias???

6)Compilacion Separada: Contratos y Modulos

