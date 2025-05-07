Estructura #3

# Funciones de String y Printing

---

## 1. Describa el por qué y para qué se utiliza

En Kotlin, las funciones de String y las operaciones de impresión son esenciales para la manipulación 
de texto y la comunicación con el usuario en aplicaciones.

# Strings en kotlin:

Un String en Kotlin representa una colección de caracteres. Las cadenas son inmutables, lo que significa 
que una vez creadas, no se pueden modificar, garantizando así la integridad de los datos.

- Se pueden crear utilizando comillas dobles **""**, lo que permite incluir cualquier tipo de texto.
- Permiten realizar operaciones como **concatenación, búsqueda y reemplazo de texto**.
- Soportan la interpolación, lo que permite insertar variables y expresiones directamente dentro de la cadena, mejorando la legibilidad del código.

# Printing en kotlin:

La impresión en Kotlin es fundamental para comunicar información al usuario a través de la consola.

# Funciones principales para imprimir en Kotlin:

- **print():** Utilizada para mostrar un mensaje en la consola sin añadir un salto de línea, lo que permite que el siguiente mensaje aparezca en la misma línea.
- **println():** Se utiliza para mostrar un mensaje en la consola y automáticamente añade un salto de línea al final, lo que organiza la salida y mejora la claridad al separar diferentes mensajes.

---

## 2. Genere un ejemplo internamente en el recuadro

- Utilice un editor de código para lograrlo.
- [🔗 Link del Código](https://pl.kotl.in/mHDqkdWz0) <!-- Aquí puedes reemplazar # por el enlace real de tu archivo en GitHub -->

---

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](#)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/6db4fd3776e313f94eecd3e12e7f09b559c94157/Variables/Variables.jpeg)

---

# Escribe una nota del cómo funciona la estructura

fun main() {
    // Información sobre un vehículo
    var marca: String = "Toyota"                // Variable mutable para la marca del vehículo
    var modelo: String = "Corolla"              // Variable mutable para el modelo del vehículo
    var anioFabricacion: Int = 2018             // Variable mutable para el año de fabricación
    var kilometraje: Double = 45000.5           // Variable mutable para el kilometraje recorrido
    var enVenta: Boolean = true                  // Variable mutable para saber si está en venta

    // Variables inmutables (no pueden cambiar)
    val tipoComburible: String = "Gasolina"     // Variable inmutable para tipo de combustible
    val numeroPuertas: Int = 4                   // Variable inmutable para número de puertas

    // Imprimir los valores con println
    println("Marca: $marca")
    println("Modelo: $modelo")
    println("Año de fabricación: $anioFabricacion")
    println("Kilometraje: $kilometraje km")
    println("¿Está en venta?: $enVenta")
    println("Tipo de combustible: $tipoComburible")
    println("Número de puertas: $numeroPuertas")

    // Modificar variables mutables
    marca = "Honda"
    anioFabricacion = 2020

    // Mensaje final
    println("La nueva marca es $marca")
    println("Y el nuevo año de fabricación es $anioFabricacion")
}

# Resultado en Consola:

- **Marca:** Toyota
- **Modelo:** Corolla
- **Año de fabricación:** 2018
- **Kilometraje:** 45000.5 km
- **¿Está en venta?:** true
- **Tipo de combustible:** Gasolina
- **Número de puertas:** 4
- Este vehículo es un Toyota Corolla, fabricado en el año 2018, y tiene un kilometraje de 45000.5 km.
- **Nueva marca:** Honda
- **Nuevo año de fabricación:** 2020


# Explicación:

Este proyecto contiene un sencillo programa en Kotlin que muestra el uso de variables mutables e inmutables, 
junto con las funciones básicas para imprimir texto en consola, print() y println().

- **Variables mutables (var)**: Se usan para valores que pueden cambiar durante la ejecución, como la marca y año de fabricación del vehículo.
- **Variables inmutables (val)**: Se emplean para datos constantes que no cambian, como el tipo de combustible y número de puertas.
- **Función println():** Imprime texto en consola y añade un salto de línea al final, ideal para mostrar cada dato en una línea separada.
- **Función print():**  Imprime texto sin añadir salto de línea, lo cual permite concatenar varios fragmentos de texto en una única línea antes de agregar un salto de línea manual.
- **Combinación de Print() y Println():** Se muestra cómo mezclar ambas funciones para construir mensajes dinámicos más elaborados, permitiendo controlar cuándo se insertan saltos de línea.

Este ejemplo sirve para entender cómo trabajar con datos y mostrar información al usuario utilizando las funciones básicas de impresión en Kotlin.

