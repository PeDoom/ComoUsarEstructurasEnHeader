# Como usar estructuras en C
En este repo se explica como usar estructuras dentro de un archivo de cabecera en C.

## Declarar estructura 

primero definimos la estructura dentro del header, en este caso estructura.h

este debe ir de la siguiente manera.
### estructura.h
```
#ifdef ESTRUCTURA_H
#infdef ESTRUCTURA_H
#define ESTRUCTURA_H
#endif

struct carro
{
	float peso;
	char marca[10];
	int age;
};
```

### Explicación 
Con este bloque de código nos aseguramos de que nuestro archivo de cabecera
funcione correctamente.

```
#ifdef ESTRUCTURA_H
#infdef ESTRUCTURA_H
#define ESTRUCTURA_H
#endif
```

En este otro segmento, declaramos la estructura.
```
struct carro
{
	float peso;
	char marca[10];
	int age;
};
```
La palabra reservada ***struct*** indica que 
los siguientes elementos agrupados entre llaves formarán una estructura.

## Definir estructura

Creamos un archivo con el nombre ***estructura.c*** el en cuál definiremos la estructura y
los metodos necesarias para la aplicación.

```
#include "estructura.h"

struct carro carro1 = {12, "noissan", 2022};

void datosCarro()
{
	printf("El peso del carro es : %.2f sumarca es : %s  y su año de fabricacion es : %i", carro1.peso, carro1.marca, carro1.age);
}
```

Se usan comillas en el ***#include "estructura.h"***  ya que estamos trabando con un archivo a nivel local, es décir en ls misma carpeta donde
se almacena ***estructura.c***.

El signo % que encontramos en el printf es un identificador de formato,[Investiga mas aquí!](https://learn.microsoft.com/es-es/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions?view=msvc-170).

## Ejecución del código 

Creamos el archivo ***main.c***
la cual contendrá nuestra función principal y llamaremos la función para ver los datos.

### main.c

```
#include <stdio.h>
#include "estructura.c"

int main()
{
	datosCarro();
}
```

En nuestro **main.c*** incluiremos ***estructura.c** 
donde previamente se definieron los métodos necesarios.

con ***datosCarros();*** llamamos el método para ver los valores almacenados en nuestra estructura.

finalmente compilamos y ejecutamos la aplicación, debería verse algo así:

***
El peso del carro es : 12.00 sumarca es : noissan  y su año de fabricacion es : 2022
[Program finished]
***





