**********************************************
		   DEBUG
**********************************************

******add_arrays_dynamic*******

1º- gcc add_arrays_dynamic.c -o add_arrays_dynamic.e
2º- .\add_arrays_dynamic.e -->(me da un resultado absurdo pero no lo toma como error)
3º- gdb add_arrays_dynamic.e
4º- <gdb>run

No detecta error

******add_arrays_segfault*******

1º- gcc add_arrays_segfault.c -o add_arrays_segfault.e
2º- .\add_arrays_segfault.e 
3º- gdb add_arrays_segfault.e
4º- <gdb>run

salta el error pero no da detalles del mismo

USANDO el flag -g

1º- gcc -g add_arrays_segfault.c -o add_arrays_segfault.e
2º- .\add_arrays_segfault.e 
3º- gdb add_arrays_segfault.e
4º. <gdb>run

DETALLE:
	
Program received signal SIGSEGV, Segmentation fault.
0x004014d8 in main (argc=1, argv=0x550ea8) at add_array_segfault.c:18
18          a[i] = i;


******************************************************

******add_arrays_static*******

1º- gcc add_arrays_static.c -o add_arrays_static.e
2º- .\add_arrays_static.e -->(me da un resultado absurdo pero no lo toma como error)
3º- gdb add_arrays_static.e
4º. <gdb>run

No detecta error

USANDO el flag -g

1º- gcc -g add_arrays_static.c -o add_arrays_static.e
2º- .\add_arrays_static.e -->(me da un resultado absurdo pero no lo toma como error)
3º- gdb add_arrays_static.e
4º- <gdb>run

no detecta error

Nota: -Wall da la misma informacion que -g

*******************************************************

******add_arrays_nobugs*******

1º- gcc add_arrays_nobugs.c -o add_arrays_nobugs.e
2º- .\add_arrays_nobugs.e -->(me da correcto el resultado)
3º- gdb add_arrays_nobugs.e
4º. <gdb>run

No detecta error

USANDO el flag -g

1º- gcc -g add_arrays_nobugs -o add_arrays_nobugs.e
2º- .\add_arrays_nobugs.e -->(me da un resultado absurdo pero no lo toma como error)
3º- gdb add_arrays_nobugs.e
4º- <gdb>run

no detecta error


*******************************************************

tambien puedo hacer: gcc -o0 -g add_arrays_nobugs -o add_arrays_nobugs.e
**************************************************

Correr el programa con un debugger, sin agregar flags de debug. ¿Tienen toda la información que requerían?

En el ejemplo no detecta el error La suma me da 182985...es decir por el valor del resultado sabemos que hay un error


¿Qué pasa si ponen el flag de debug? ¿Qué flag de optimización es el mejor para debuggear?



Agreguen algún flag para que informe todos los warnings en la compilación, como -Wall. 
¿Alguno les da alguna pista de por qué el programa se rompe?

