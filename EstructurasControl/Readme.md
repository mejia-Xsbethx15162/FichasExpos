Estructura #5

# Estructuras de Control,Decisión y Manejo de Errores en Kotlin

---

## 1. Describa el por qué y para qué se utiliza

En Kotlin, las estructuras de control, decisión y manejo de errores son fundamentales para crear programas dinámicos, robustos y eficientes. Aquí te explico el por qué y el para qué de cada una:

# Estructuras de Control:

# ¿Por qué se utilizan?

Porque permiten repetir acciones o ejecutar bloques de código múltiples veces bajo ciertas condiciones.

# ¿Para qué se utilizan?

- Para automatizar tareas repetitivas (como imprimir una lista de números).
- Para recorrer listas, arrays o colecciones.
- Para ejecutar un código hasta que se cumpla una condición.

# Ejemplos en Kotlin:

- **for** – Itera sobre un rango o colección.
- **while** – Repite un bloque mientras una condición sea verdadera.
- **do...while** – Ejecuta el bloque al menos una vez antes de verificar la condición.

# Estructuras de Decisión

# ¿Por qué se utilizan?

Porque los programas deben tomar decisiones basadas en condiciones reales (como el valor de una variable).

# ¿Para qué se utilizan?

- Para ejecutar diferentes bloques de código según el caso.
- Para controlar el flujo del programa según los datos de entrada.

# Ejemplos en Kotlin:

- **if / else if / else** – Ejecuta bloques según condiciones booleanas.

- **when** – Alternativa más clara a múltiples if-else (parecido a switch en otros lenguajes).

# Manejo de Errores (Excepciones)
 
# ¿Por qué se utilizan?

Porque en la vida real los errores ocurren (como intentar dividir entre cero o leer un archivo que no existe) y debemos anticiparlos.

# ¿Para qué se utilizan?

- Para prevenir que el programa se detenga inesperadamente.
- Para dar una respuesta útil o controlada al usuario ante errores.
- Para depurar o registrar fallos en tiempo de ejecución.

# Ejemplo en Kotlin:

// try {
    val resultado = 10 / 0
} catch (e: ArithmeticException) {
    println("Error: División por cero")
} finally {
    println("Este bloque siempre se ejecuta")
//}

---

## 2. Genere un ejemplo internamente en el recuadro

- Utilice un editor de código para lograrlo.
- [🔗 Link del Código](https://pl.kotl.in/JEVPjP0g5) <!-- Aquí puedes reemplazar # por el enlace real de tu archivo en GitHub -->

---

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](#)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/5ab91d5d79958a2c6f59d749acae4d6f6ff924e2/EstructurasControl/EstructuraControl.png)

---

# Escribe una nota del cómo funciona la estructura

fun main() {

    // Lista de entradas simuladas, como si el usuario las escribiera por consola
    // Incluye valores válidos, inválidos ("error") y un número negativo para terminar
    val entradas = listOf("12", "7", "error", "-1", "4")

    // Variable para llevar el control del índice actual de la lista de entradas
    var i = 0

    // Estructura de control: ciclo while que recorre cada entrada simulada
    while (i < entradas.size) {
        // Obtener la entrada actual de la lista
        val entrada = entradas[i]
        println("Entrada simulada: $entrada")

        // Estructura de manejo de errores: intentar convertir la entrada a entero
        try {
            val numero = entrada.toInt()  // Puede lanzar excepción si no es número

            // Estructura de decisión: si el número es negativo, termina el programa
            if (numero < 0) {
                println("¡Número negativo detectado! Fin del programa.")
                break  // Rompe el ciclo y termina
            }

            // Estructura de decisión: verifica si el número es múltiplo de 3
            if (numero % 3 == 0) {
                println("El número $numero es múltiplo de 3.")
            } else {
                println("El número $numero NO es múltiplo de 3.")
            }

        } catch (e: NumberFormatException) {
            // Si la conversión falla, se muestra un mensaje de error
            println("Error: '$entrada' no es un número válido.")
        }

        // Incrementa el contador para continuar con la siguiente entrada
        i++
    }
}


# Resultado en Consola:

- **Entrada simulada:** 12
- El número 12 es múltiplo de 3.
- **Entrada simulada:** 7
- El número 7 NO es múltiplo de 3.
- **Entrada simulada:** error
- **Error:** 'error' no es un número válido.
- **Entrada simulada:** -1
- ¡Número negativo detectado! Fin del programa.


# Explicación:

Este programa en Kotlin muestra cómo aplicar estructuras de decisión (if), control (while) y manejo de errores (try-catch) 
en un flujo de ejecución que simula entradas del usuario.

- **Estructura de Control (while):** Se usa para repetir un bloque de instrucciones mientras haya entradas en la lista.
- **Estructura de Decisión (if, else):** Evalúa si un número es múltiplo de 3 y también si es negativo.
- **Manejo de Errores (try-catch):** Captura cualquier intento fallido de conversión cuando una entrada no es un número (por ejemplo, "error").
- **Entradas simuladas:** En lugar de usar readLine(), se utiliza una lista de valores simulados para que funcione correctamente en el entorno en línea.
- Este ejemplo sirve para entender cómo trabajar con datos y mostrar información al usuario utilizando las funciones básicas de impresión en Kotlin.
