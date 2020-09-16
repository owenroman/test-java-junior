# Ejercicio para evaluación de candidatos para Developers Java - Nivel Junior

# 1. Análisis e Interpretación de Código

Analizar el siguiente bloque de código ¿Es un programa Java válido? ¿Compila? Si es así, indicar el resultado de su ejecución y explicar por qué el resultado es el indicado

```java
    String letra = "6";
    String prefijo = "Iteracion nro ";
    for (int i = 0; i < 10; i++) {
        if (letra == String.valueOf(i)) {
            System.out.println("El bucle continua");
            break;
        } else {
            System.out.println(prefijo + i);
        }
    }
```
El codigo compila bien pero no cumple su cometido, que sería finalizar el programa cuando el índice 'i' llegue a 6.
Esto porque la variable "letra", que contiene la condición 'if' como un parámetro, es de tipo string y no se hace una correcta conversión de datos.<br>
Una solución a este problema podría ser cambiar el tipo de variable para "letra",o bien utilizar la siguiente sintaxis de conversion de datos:<br><br>

```
int <IntVariableName> = Integer.parseInt (<StringVariableName>);
``` 

Adjunto código de posible solución.

```
public class ejercicio {
	public static void main (String[]Args) {
		String letra = "6";
		String prefijo = "Iteracion nro ";
		int aux=Integer.parseInt(letra);
		for (int i = 0; i < 10; i++) {	
			if ( aux==i) {
				System.out.println("El bucle continua");
				break;
			} else {
				System.out.println(prefijo + i);
			}
		}
	}
}
``` 

# 2. Modelado OO

Escribir un aplicativo Java que permita administrar un catálogo de automóviles bajo los siguientes requisitos:

Se necesita poder representar automóviles, donde se guardarán las siguientes características por automovil: color, puertas, ruedas, kilometraje, número de chasís, marca.

Los automóviles deben poder simular las operaciones de acelerar, frenar, prenderse y apagarse.

También debe modelarse automóviles especiales tipo deportivos, que compartan todas las características de un automóvil normal, pero además se pueda conocer la cantidad de segundos que le toma llegar de 0 a 100 Km/h.

Se debe poder construir un automóvil pasando de parámetros sus principales características: color, puertas, ruedas, kilometraje, número de chasis, marca.

Una vez modelado el sistema se debe poder interactuar con el aplicativo por línea de comandos y realizar las siguientes operaciones:

* Ofrecer una lista de autos ya precargados, mostrando su marca, color, nro de chasis y si es deportivo
* Permitir de la lista anterior buscar y seleccionar un auto por medio de su nro de chasis
* Permitir conducir el auto seleccionado ofreciendo las operaciones de: acelerar, frenar, prenderse y apagarse.
* Si se acelera un auto deportivo se debe imprimir en consola la cantidad de segundos que le toma llegar de 0 a 100 Km/h

🎁 _Bono:_ se ofrecerá un punto de bono si se lee la lista de autos a partir de un archivo de texto.

# 3. Conexión JDBC

Conectarse a una base de datos por JDBC, hacer una consulta mediante un PreparedStatement e imprimir en consola los resultados de la consulta.

El sistema debe modelar y comportarse según las siguientes especificaciones:

1.  Debe permitir ingresar por parámetros de aplicación o por consola el nombre de la columna y el valor a consultar de la columna

2.  Debe ejecutar un query de acuerdo a los datos ingresados en el ítem 1 e impirmir en consola el resultado del query. Los parámetros deben ser usados para armar el query de la siguiente forma:

    `select * from potluck where nombreColumnaParam = valorParam`

    Donde nombreColumnaParam y valorParam son los parámetro del ítem 1.

3.  Se debe utilizar un PreparedStatement para setear el valor usado como filtro del query. No vale concatenar todo en un string.

Se puede utilizar el siguiente script SQL compatible con PostgreSQL para crear la tabla:

```sql
CREATE TABLE potluck
(
    id integer NOT NULL,
    name character varying(20),
    food character varying(30),
    confirmed character(1),
    signup_date date,
    CONSTRAINT potluck_pkey PRIMARY KEY (id )
)
```


