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
  
- [🔗 Link del audio](https://github.com/mejia-Xsbethx15162/FichasExpos/raw/refs/heads/main/ControlFlujo/ControlFlujo.ogg)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/450cc72e72a0057ce5e1e463c114a505237c5815/ControlFlujo/controles%20de%20flujoIfBucles.png)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/be1d2c1cd0e5e4d89646a567a6c122c9b831328b/ControlFlujo/controles%20de%20flujo2.png)

---

# Escribe una nota del cómo funciona la estructura

// fun main() {

        // Declaración de una variable entera
    var numero = 7                             // Valor inicial del número a evaluar

    // Condicionales if - else if - else
    if (numero > 0) {                          // Si el número es mayor que 0
        println("El número es positivo.")      // Imprime que es positivo
    } else if (numero < 0) {                   // Si el número es menor que 0
        println("El número es negativo.")      // Imprime que es negativo
    } else {                                   // Si no es mayor ni menor que 0, entonces es igual a 0
        println("El número es cero.")          // Imprime que es cero
    }

    // Bucle while
    var contador = 1                           // Inicializa contador en 1
    println("Contando del 1 al 5 con while:")
    while (contador <= 5) {                    // Mientras contador sea menor o igual a 5
        println("Contador: $contador")         // Imprime el valor actual de contador
        contador++                             // Incrementa el contador en 1
    }

    // Bucle for con rango
    println("Contando del 1 al 5 con for:")
    for (i in 1..5) {                          // Recorre un rango del 1 al 5 (incluyendo ambos extremos)
        println("Valor de i: $i")              // Imprime el valor de i en cada iteración
    }

    // Bucle for con condición dentro
    println("Números pares del 1 al 10:")
    for (i in 1..10) {                         // Recorre los números del 1 al 10
        if (i % 2 == 0) {                      // Si el número es divisible entre 2
            println("$i es par")               // Imprime que es par
        }
    }

    // Bucle con break y continue
    println("Uso de break y continue:")
    for (i in 1..10) {
        if (i == 3) continue                   // Si i es 3, salta a la siguiente iteración
        if (i == 7) break                      // Si i es 7, rompe (termina) el bucle
        println("Número válido: $i")           // Imprime valores del 1 al 6, excepto el 3
    }
// }


# Resultado en Consola:

El número es positivo.
**Contando del 1 al 5 con while:**
- **Contador:** 1
- **Contador:** 2
- **Contador:** 3
- **Contador:** 4
- **Contador:** 5
**Contando del 1 al 5 con for:**
- **Valor de i:** 1
- **Valor de i:** 2
- **Valor de i:** 3
- **Valor de i:** 4
- **Valor de i:** 5
**Números pares del 1 al 10:**
- 2 es par
- 4 es par
- 6 es par
- 8 es par
- 10 es par
**Uso de break y continue:**
- **Número válido:** 1
- **Número válido:** 2
- **Número válido:** 4
- **Número válido:** 5
- **Número válido:** 6


# Explicación:

- Primero declaramos una variable entera numero con el valor 7 para evaluarla.
- Usamos una estructura if - else if - else para verificar si el número es positivo, negativo o cero.
- Luego, declaramos una variable contador para demostrar un bucle while, que imprime los números del 1 al 5.
- A continuación, utilizamos un bucle for con un rango (1..5) para contar del 1 al 5 e imprimir cada valor.
- Después, usamos otro for con una condición para imprimir únicamente los números pares del 1 al 10.
- Finalmente, mostramos cómo usar break y continue en un bucle for:
- continue salta el número 3.
- break termina el bucle cuando llega al número 7.
- Todos los resultados se muestran con println, permitiendo observar el flujo de ejecución y el comportamiento de cada tipo de bucle o condición.

