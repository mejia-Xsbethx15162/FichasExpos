Estructura #9

# Arrays

---

## 1. Describa el por qué y para qué se utiliza

Los arrays en Kotlin (y en la mayoría de los lenguajes de programación) son estructuras de datos fundamentales que se utilizan por razones específicas y para propósitos bien definidos.

**¿Por Qué usar Arrays?**

- **Acceso Rápido:** Elementos contiguos permiten acceso directo por índice en tiempo constante. **¿Para qué?** Lectura veloz de datos por posición.
- **Orden Natural:** Representan directamente secuencias ordenadas de longitud fija. **¿Para qué?** Almacenar listas donde el orden importa.
- **Optimización Primitiva:** IntArray, etc., evitan "boxing" para mejor rendimiento y memoria. **¿Para qué?** Trabajar eficiente con grandes cantidades de datos simples.
- **Base de Estructuras:** Sirven como cimiento para listas dinámicas, pilas, etc. **¿Para qué?** Construir herramientas de organización de datos más complejas.

**¿Para Qué usar Arrays?**

- Colecciones de tamaño fijo/conocido.
- Acceso frecuente por índice.
- Implementar algoritmos indexados.
- Interoperar con Java.
- Optimizar memoria para primitivos.
- Representar tablas/matrices.

---

## 2. Genere un ejemplo internamente en el recuadro

- Utilice un editor de código para lograrlo.
- [🔗 Link del Código](https://pl.kotl.in/ai9S6b-f1) <!-- Aquí puedes reemplazar # por el enlace real de tu archivo en GitHub -->

---

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](https://github.com/mejia-Xsbethx15162/FichasExpos/raw/refs/heads/main/Arrays/Arrays.ogg)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/770e9d106cd9513a67b33b92f4b04340e2b0c28b/Arrays/Arrays.png)

---

# Escribe una nota del cómo funciona la estructura

fun main() {

    val numeros = intArrayOf(5, 12, 8, 21, 3, 15, 10, 7, 18, 9)
    println("Array original: ${numeros.joinToString()}")

    // 1. Calcular el promedio
    val promedio = numeros.average()
    println("\nPromedio: ${"%.2f".format(promedio)}")

    // 2. Encontrar el valor máximo y mínimo
    val maximo = numeros.maxOrNull()
    val minimo = numeros.minOrNull()
    println("Máximo: $maximo, Mínimo: $minimo")

    // 3. Filtrar números pares
    val pares = numeros.filter { it % 2 == 0 }
    println("\nNúmeros pares: ${pares.joinToString()}")

    // 4. Transformar cada número a su cuadrado
    val cuadrados = numeros.map { it * it }.toIntArray()
    println("\nCuadrados: ${cuadrados.joinToString()}")

    // 5. Encontrar pares que suman un valor específico (ejemplo: 20)
    val valorObjetivo = 20
    val paresQueSuman = mutableListOf<Pair<Int, Int>>()
    for (i in numeros.indices) {
        for (j in i + 1 until numeros.size) { // Evitar duplicados y comparar un número consigo mismo
            if (numeros[i] + numeros[j] == valorObjetivo) {
                paresQueSuman.add(Pair(numeros[i], numeros[j]))
            }
        }
    }
    println("\nPares que suman $valorObjetivo: ${paresQueSuman.joinToString()}")

    // 6. Ordenar el array de forma descendente
    numeros.sortDescending()
    println("\nArray ordenado descendentemente: ${numeros.joinToString()}")

    // 7.  Verificar si el array contiene el número 15
    val contiene15 = numeros.contains(15)
    println("\n¿Contiene el número 15?: $contiene15")
}

# Resultado en Consola:

- **Array original:** 5, 12, 8, 21, 3, 15, 10, 7, 18, 9
- **Promedio:** 10.80
- **Máximo:** 21, Mínimo: 3
- **Números pares:** 12, 8, 10, 18
- **Cuadrados:** 25, 144, 64, 441, 9, 225, 100, 49, 324, 81
- **Pares que suman 20:** (5, 15), (12, 8)
- **Array ordenado descendentemente:** 21, 18, 15, 12, 10, 9, 8, 7, 5, 3
- **¿Contiene el número 15?:** true


# Explicación:

- **`average()`:** Calcula el promedio de los elementos.
- **`maxOrNull()`, `minOrNull()`:** Encuentran el máximo y mínimo, respectivamente.  `OrNull` previene errores si el array está vacío.
- **`filter { ... }`:** Crea un nuevo array con los elementos que cumplen la condición.
- **`map { ... }.toIntArray()`:** Transforma cada elemento (a su cuadrado) y lo convierte a `IntArray`.
- **Algoritmo para encontrar pares:** Un bucle anidado verifica todas las combinaciones de pares.
- **`sortDescending()`:** Ordena el array *in-place* en orden descendente.
- **`contains(...)`:** Verifica si el array contiene un elemento específico.
