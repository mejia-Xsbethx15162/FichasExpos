Estructura #8

# Programación funcional y exepciones Lambda

---

## 1. Describa el por qué y para qué se utiliza

El paradigma de la programación funcional se adopta en Kotlin por varias razones fundamentales que apuntan a mejorar la calidad, la seguridad y la expresividad del código.

## **Programación Funcional (PF) en Kotlin: ¿Por Qué?**

- **Seguridad:** Datos inmutables evitan errores inesperados y facilitan la concurrencia. ¿Para qué? Sistemas robustos.
- **Flexibilidad:** Funciones como valores permiten componer lógica y abstraer comportamiento.
  
**¿Para qué?**
  
- **Código modular y reutilizable.**
- **Claridad:** Operaciones declarativas sobre datos mejoran la lectura. ¿Para qué? Desarrollo eficiente y código entendible.
- **Pruebas:** Sin efectos secundarios, las funciones son fáciles de testear. ¿Para qué? Software de calidad y refactorización segura.
  
## **Excepciones Lambda en Kotlin: ¿Por Qué?**

- **Flexibilidad en Funciones de Orden Superior:** Las lambdas no declaran excepciones comprobadas para ser compatibles con diversas funciones. ¿Para qué? Reutilización amplia de funciones de orden superior.
- **Propagación Estándar:** Las excepciones en lambdas se propagan como en el código regular.

**¿Para qué?**
- **Manejo de errores consistente.**
- **Manejo Específico Necesario:** Se usan try-catch dentro o lógica en la función de orden superior. **¿Para qué?** Aplicaciones robustas que gestionan errores en código funcional.

---

## 2. Genere un ejemplo internamente en el recuadro

- Utilice un editor de código para lograrlo.
- [🔗 Link del Código](https://pl.kotl.in/SpyRCw-6c) <!-- Aquí puedes reemplazar # por el enlace real de tu archivo en GitHub -->

---

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](#)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/c8ffe86759ba17bb1082e7b2f25b3a55f67a79b7/Programaci%C3%B3nFuncional/Programaci%C3%B3nExpLambdas.png)

---

# Escribe una nota del cómo funciona la estructura

// import kotlin.math.pow

fun main() {

    val valores = listOf("2", "3", "a", "4.5", "5")
    val potencia = 2.0
    val resultados = mutableListOf<Double>()
    val errores = mutableListOf<Pair<String, String>>()

    val calcularPotencia: (String, Double) -> Double? = { valorStr, exponente ->
        try {
            val numero = valorStr.toDouble()
            numero.pow(exponente)
        } catch (e: NumberFormatException) {
            errores.add(Pair(valorStr, "No es un número válido para calcular la potencia."))
            null
        } catch (e: Exception) {
            errores.add(Pair(valorStr, "Error inesperado al calcular la potencia: ${e.message}"))
            null
        }
    }

    valores.forEach { valor ->
        calcularPotencia(valor, potencia)?.let { resultado ->
            resultados.add(resultado)
        }
    }

    println("--- Cálculo de Potencias ---")
    println("Valores originales: $valores")
    println("Potencia utilizada: $potencia")
    println("Resultados válidos: $resultados")

    if (errores.isNotEmpty()) {
        println("\n--- Errores Encontrados ---")
        errores.forEach { (valor, error) ->
            println("Valor: '$valor', Error: $error")
        }
    } else {
        println("\nNo se encontraron errores durante el cálculo.")
    }

    // Ejemplo adicional: Usando map y una lambda para el mismo propósito
    val resultadosConMap = valores.mapNotNull { valorStr ->
        try {
            valorStr.toDouble().pow(potencia)
        } catch (e: NumberFormatException) {
            println("Advertencia (map): No se pudo convertir '$valorStr' a número.")
            null
        }
    }
    println("\n--- Resultados con mapNotNull ---")
    println("Resultados válidos (usando mapNotNull): $resultadosConMap")
}

# Resultado en Consola:

**--- Cálculo de Potencias ---**

- **Valores originales:** [2, 3, a, 4.5, 5]
- **Potencia utilizada:** 2.0
- **Resultados válidos:** [4.0, 9.0, 20.25, 25.0]

**--- Errores Encontrados ---**
- **Valor: 'a', Error:** No es un número válido para calcular la potencia.
- **Advertencia (map):** No se pudo convertir 'a' a número.

**--- Resultados con mapNotNull ---**
- **Resultados válidos (usando mapNotNull):** [4.0, 9.0, 20.25, 25.0]


# Explicación:

- **`valores`:** Una lista de strings, algunos de los cuales representan números válidos y otros no.
- **`potencia`:** El exponente al que se elevarán los números.
- **`resultados` y `errores`:** Listas mutables para almacenar los resultados válidos del cálculo de la potencia y los errores encontrados, respectivamente.
- **`calcularPotencia: (String, Double) -> Double?`:** Se define una función lambda con tipo explícito que toma un `String` (el valor) y un `Double` (la potencia) como argumentos y devuelve un `Double?` (nullable Double). 
     Esto permite devolver `null` en caso de error.
- **`try-catch` dentro de la Lambda:** La lambda intenta convertir el `valorStr` a `Double` y calcular su potencia. Si ocurre una `NumberFormatException` o cualquier otra excepción, se captura el error, se añade un 
     mensaje a la lista `errores`, y se devuelve `null`.
- **`forEach` y `let`:** Se itera sobre la lista `valores`. Para cada `valor`, se llama a la lambda `calcularPotencia`. El resultado (que puede ser un `Double` o `null`) se maneja con `.let`. Si el resultado no es `null`, 
     se añade a la lista `resultados`.
- **Manejo de Errores:** Después de procesar todos los valores, se imprimen los resultados válidos y, si hay errores en la lista `errores`, se imprimen los detalles de cada error.
- **Ejemplo con `mapNotNull`:** Se incluye un ejemplo adicional usando la función de orden superior `mapNotNull`. `mapNotNull` combina la operación de mapeo (aplicar la lambda para calcular la potencia) con el filtrado de 
    resultados nulos (los que generaron una excepción). Esto proporciona una forma más concisa de lograr un resultado similar.

Este ejemplo ilustra cómo usar una lambda para encapsular una operación que puede lanzar excepciones y cómo manejar esas excepciones dentro del flujo de la programación funcional, utilizando funciones
como `forEach` con `let` o `mapNotNull` para procesar los resultados de manera segura y registrar los errores.
