# Introducción al lenguaje de programación Java
#### ¿Q# Introducción al lenguaje de programación Java
#### ¿QUÉ ES JAVA?
La tecnología de Java es un lenguaje de programación y una plataforma comercializada por primera vez en 1995 por Sun Microsystems.
La sintaxis de Java deriva en gram medida de C y C++, pero tiene menos utilidades de bajo nivel que cualquiera de ellos. El lenguaje de programación Java es un lenguaje de alto nivel, orientado a objetos.
##### JDK
El Java Development Kit (JDK) proporciona el conjunto de herramientas básico para el desarrollo de aplicaciones con Java estándar.
##### INTRODUCCIÓN
A pesar que aún carecemos del conocimiento del lenguaje, podemos iniciar con un sencillo programa en Java que servirá para conocer el procedimiento general que se debe seguir para crear, compilar y ejecutar programas en Java.

Utilizando cualquier editor de texto procedemos a capturar el código (teniendo en cuenta que Java es sensitivo a mayúsculas y minúsculas).
```java
public class HolaMundo {
		public static void main(String[]args){
				System.out.println("Hola Mundo");
		}
}
```
Después procedemos a guardar este programa en un archivo de texto llamado **HolaMundo.Java** (el nombre debe ser el mismo que el de la clase).
##### IDE
Un **IDE** (Integrated Development Environment) es una aplicación que facilita el desarrollo de apliaciones en algún lenguaje de programación.
En el mercado existen diversos tipos de **IDE**, cada uno con caracteristicas propias, una constante es que te permiten manejar las etapas para generar un programa dependiendo del tipo de lenguaje utilizado.
Ejemplos:
- Eclipse
- NetBeans
- ¡Edit

# ESTRUCTURA DE UN PROGRAMA
Todo programa Java debe estar escrito en una o varias **clases**, dentro de las cuales se podrá hacer uso del amplio conjunto de paquetes y clases prediseñadas.

Una de las mejores caracteristicas de Java es que es un lenguaje totalmente orientado a objetos.
Java consta de una clase principal (que contiene el metodo main) y algunas clases del usuario, que luego son usadas por el programa o clase principal.
  La clase principal debe ser declarada con el modificador de acceso public y la palabra reservada class, seguida del nombre de la clase iniciando con mayuscula.
  
**Ejemplo:**
```java
clase pública MiClase{
  		public static void main(String[] args){
    			System.out.println("Esta es mi clase");
  	}
}
```
#### El metodo main
En la clase principal debe existir una **función o método**  estático llamado **main** cuyo formato debe ser:
```java
public static void main(String[]args)
```
El metodo main es el punto de arranque de un programa en Java.
#### **Comentarios, identificadores y palabras reservadas**
**Comentarios:** Son muy útiles para poder entender el código utilizado, facilitando de ese modo futuras revisiones y correciones.
En Java existen tres tipos de comentarios:
1. Comentarios de una sola línea:
```java
//Esta es una línea comentada en Java
```
2. Comentarios de bloques:
```java
/* Aquí empieza el
bloque de comentarios
y aqui acaba */
```
3. Comentarios de documentación(**JavaDoc**):
```java
/** Los comentarios de documentación se realizan de este modo*/
```

**Identificadores:** En Java los identificadores comienzan por una letra del alfabeto inglés, un subrayado _ o el símbolo de dólar $.
**Palabras reservadas:** Son utilizadas por Java y no pueden ser usadas como identificadores.

UÉ ES JAVA?
La tecnología de Java es un lenguaje de programación y una plataforma comercializada por primera vez en 1995 por Sun Microsystems.
La sintaxis de Java deriva en gram medida de C y C++, pero tiene menos utilidades de bajo nivel que cualquiera de ellos. El lenguaje de programación Java es un lenguaje de alto nivel, orientado a objetos.
##### JDK
El Java Development Kit (JDK) proporciona el conjunto de herramientas básico para el desarrollo de aplicaciones con Java estándar.
##### INTRODUCCIÓN
A pesar que aún carecemos del conocimiento del lenguaje, podemos iniciar con un sencillo programa en Java que servirá para conocer el procedimiento general que se debe seguir para crear, compilar y ejecutar programas en Java.

Utilizando cualquier editor de texto procedemos a capturar el código (teniendo en cuenta que Java es sensitivo a mayúsculas y minúsculas).
```java
public class HolaMundo {
		public static void main(String[]args){
				System.out.println("Hola Mundo");
		}
}
```
Después procedemos a guardar este programa en un archivo de texto llamado **HolaMundo.Java** (el nombre debe ser el mismo que el de la clase).
##### IDE
Un **IDE** (Integrated Development Environment) es una aplicación que facilita el desarrollo de apliaciones en algún lenguaje de programación.
En el mercado existen diversos tipos de **IDE**, cada uno con caracteristicas propias, una constante es que te permiten manejar las etapas para generar un programa dependiendo del tipo de lenguaje utilizado.
Ejemplos:
- Eclipse
- NetBeans
- ¡Edit

# ESTRUCTURA DE UN PROGRAMA
Todo programa Java debe estar escrito en una o varias **clases**, dentro de las cuales se podrá hacer uso del amplio conjunto de paquetes y clases prediseñadas.

Una de las mejores caracteristicas de Java es que es un lenguaje totalmente orientado a objetos.
Java consta de una clase principal (que contiene el metodo main) y algunas clases del usuario, que luego son usadas por el programa o clase principal.
  La clase principal debe ser declarada con el modificador de acceso public y la palabra reservada class, seguida del nombre de la clase iniciando con mayuscula.
  
**Ejemplo:**
```java
clase pública MiClase{
  		public static void main(String[] args){
    			System.out.println("Esta es mi clase");
  	}
}
```
#### El metodo main
En la clase principal debe existir una **función o método**  estático llamado **main** cuyo formato debe ser:
```java
public static void main(String[]args)
```
El metodo main es el punto de arranque de un programa en Java.
#### Comentarios, identificadores y palabras reservadas
