Estructura #4

# Control de Flujo:

---

## 1. Describa el por qué y para qué se utiliza

El control de flujo es un concepto esencial en la programación que permite dirigir el flujo de ejecución 
del código según condiciones específicas. Esto se logra a través de estructuras como condicionales y bucles.

# Por qué utilizar Control de Flujo:

- **Toma de Decisiones:**

Permite al programa tomar decisiones basadas en condiciones (por ejemplo, si un vehículo está en venta, mostrar información adicional).

- **Repetición de Acciones:**

Facilita la ejecución repetida de bloques de código (por ejemplo, procesar una lista de vehículos).

- **Mejorar la Eficiencia:**

Optimiza el rendimiento controlando qué partes del código se ejecutan bajo ciertas condiciones.

# Para qué utilizar Control de Flujo:

- **Condicionales:**

Permiten ejecutar diferentes bloques de código según ciertas condiciones (if, else).

- **Bucles:**

Repetición de acciones hasta que se cumpla una condición (for, while).

- **Manejo de Errores:**

Asegura que el código responda correctamente ante situaciones inesperadas, evitando fallos.

---

## 2. Genere un ejemplo internamente en el recuadro.

- Utilice un editor de código para lograrlo.
  [🔗 Link del Código](https://pl.kotl.in/uSaGi8uPl)

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](#)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/450cc72e72a0057ce5e1e463c114a505237c5815/ControlFlujo/controles%20de%20flujoIfBucles.png)
-  [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/450cc72e72a0057ce5e1e463c114a505237c5815/ControlFlujo/controles%20de%20flujoIfBucles.png)

---

# Escribe una nota del cómo funciona la estructura

// fun main() {

    // Variables mutables inicializadas con números decimales (Double)
    var x: Double = 15.75                     // Declaración de variable mutable x con valor 15.75
    var y: Double = 4.2                       // Declaración de variable mutable y con valor 4.2

    // Operadores aritméticos básicos
    val suma = x + y                          // Suma de x e y
    val resta = x - y                         // Resta de y a x
    val multiplicacion = x * y                // Multiplicación de x e y
    val division = x / y                      // División de x entre y
    val modulo = x % y                        // Módulo (residuo) de x dividio entre y

    // Operadores de asignación compuesta
    x += y * 2                               // Incrementa x sumando el doble de y
    y /= 3                                  // Divide y entre 3 y actualiza su valor

    // Operadores unarios
    x++                                     // Incremento postfijo: x aumenta en 1
    --y                                     // Decremento prefijo: y disminuye en 1 antes de usarse

    // Operación combinada usando variables modificadas
    val resultadoFinal = (x + y) * (x - y) / y   // Expresión combinada de suma, resta, multiplicación y división

    // Mostrar resultados en consola
    println("Suma: $suma")
    println("Resta: $resta")
    println("Multiplicación: $multiplicacion")
    println("División: $division")
    println("Módulo: $modulo")
    println("Valor final de x: $x")
    println("Valor final de y: $y")
    println("Resultado final de la expresión combinada: $resultadoFinal")
// }


# Resultado en Consola:

- **Suma:** 19.95
- **Resta:** 11.55
- **Multiplicación:** 66.15
- **División:** 3.75
- **Módulo:** 3.15
- **Valor final de x:** 25.15
- **Valor final de y:** 0.4
- **Resultado final de la expresión combinada:** 1580.9062


# Explicación:

- Primero declaramos dos variables mutables x y y con valores decimales.
- Luego calculamos operaciones básicas entre x y y, y guardamos los resultados.
- Modificamos los valores de x y y con asignaciones compuestas y operadores unarios.
- Finalmente, calculamos una expresión matemática combinada con los valores actualizados.
- Imprimimos todos los resultados y los valores finales para ver los cambios.

