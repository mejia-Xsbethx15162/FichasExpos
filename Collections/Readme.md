Estructura #6

# Collections, json y manejo de datos

---

## 1. Describa el por qué y para qué se utiliza

En Kotlin, Collections, JSON y el manejo de datos son herramientas fundamentales para trabajar con información de forma eficiente, flexible y estructurada. 
Aquí tienes una descripción clara del por qué y el para qué se utilizan:

# Collections (Colecciones)

**¿Por qué se utilizan?**

Porque en la mayoría de las aplicaciones necesitamos agrupar y manipular múltiples valores, como listas de productos, usuarios o resultados. Kotlin ofrece una API rica y funcional para trabajar con estructuras de datos.

**¿Para qué se utilizan?**

- Para almacenar y organizar conjuntos de elementos (por ejemplo, List, Set, Map).
- Para recorrer, filtrar, ordenar y transformar datos fácilmente usando funciones como .map(), .filter(), .forEach(), etc.
- Para hacer que el código sea más conciso, seguro y legible.

- **Ejemplo:** Una lista de nombres que se filtra para mostrar solo los que empiezan por "A".

# JSON (JavaScript Object Notation)

**¿Por qué se utiliza?**

Porque JSON es el formato estándar para intercambiar datos entre sistemas, especialmente en aplicaciones web y móviles. Kotlin lo necesita para comunicarse con APIs y servicios.

**¿Para qué se utiliza?**

- Para leer y escribir datos estructurados en forma de texto plano.
- Para intercambiar información entre el cliente y el servidor (por ejemplo, al consumir una API REST).
- Con bibliotecas como kotlinx.serialization o Gson, se puede convertir JSON a objetos Kotlin (y viceversa) fácilmente.

- **Ejemplo:** Un JSON con información de un usuario ({ "nombre": "Ana", "edad": 25 }) que se transforma en un objeto Kotlin Usuario(nombre = "Ana", edad = 25).

# Manejo de Datos

**¿Por qué se utiliza?**

Porque una aplicación sin datos útiles no cumple su propósito. El manejo adecuado de datos permite que una app sea funcional, confiable y útil.

**¿Para qué se utiliza?**

- Para almacenar, validar, convertir y procesar información que ingresa o sale del sistema.
- Para evitar errores como NullPointerException, inconsistencias, o datos mal interpretados.
- Para construir modelos de datos (data class), manipular fechas, números, cadenas y mantener la integridad de la información.

- **Ejemplo:** Alguien llena un formulario, y el programa valida que todos los campos estén completos y bien formateados antes de guardarlos.

---

## 2. Genere un ejemplo internamente en el recuadro

- Utilice un editor de código para lograrlo.
- [🔗 Link del Código](https://pl.kotl.in/t-HAw0LGK) <!-- Aquí puedes reemplazar # por el enlace real de tu archivo en GitHub -->

---

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](#)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/b9950a287018f5d6b021a3cbb3107590b132f7c9/Collections/Collections.png)

---

# Escribe una nota del cómo funciona la estructura

// import java.util.LinkedList
// import java.time.LocalDateTime
// import java.time.format.DateTimeFormatter

// class TaskQueue(private val maxlen: Int? = null) {

    // `queue`: LinkedList para almacenar las tareas en orden de llegada (FIFO).
    private val queue = LinkedList<String>()
    // `history`: LinkedList para guardar el historial de las operaciones (añadido, procesado).
    private val history = LinkedList<Pair<String, String>>()
    // `formatter`: Objeto para formatear la marca de tiempo en un formato legible.
    private val formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss")

    // `addTask`: Función para añadir una nueva tarea a la cola.
    fun addTask(task: String) {
        // Verifica si se ha definido una longitud máxima y si la cola está llena.
        if (maxlen != null && queue.size >= maxlen) {
            // Si la cola está llena, remueve la tarea más antigua del frente.
            queue.removeFirst()
            println("Advertencia: La cola ha alcanzado su capacidad máxima. Se eliminó la tarea más antigua.")
        }
        // Añade la nueva tarea al final de la cola.
        queue.addLast(task)
        // Obtiene la marca de tiempo actual formateada.
        val timestamp = LocalDateTime.now().format(formatter)
        // Añade un registro al historial indicando que la tarea fue añadida y la hora.
        history.addFirst(Pair("Añadida: $task", timestamp))
        println("[${timestamp}] Tarea '$task' añadida a la cola.")
    }

    // `processTask`: Función para procesar la siguiente tarea en la cola.
    fun processTask(): String? {
        // Verifica si la cola no está vacía.
        return if (queue.isNotEmpty()) {
            // Remueve y retorna la primera tarea de la cola (FIFO).
            val task = queue.removeFirst()
            // Obtiene la marca de tiempo actual formateada.
            val timestamp = LocalDateTime.now().format(formatter)
            // Añade un registro al historial indicando que la tarea fue procesada y la hora.
            history.addFirst(Pair("Procesada: $task", timestamp))
            println("[${timestamp}] Tarea '$task' procesada.")
            task
        } else {
            // Si la cola está vacía, muestra un mensaje y retorna null.
            println("La cola está vacía. No hay tareas para procesar.")
            null
        }
    }

    // `getQueue`: Función para obtener una lista con el estado actual de la cola.
    fun getQueue(): List<String> {
        return queue.toList()
    }

    // `getHistory`: Función para obtener una lista con el historial de operaciones.
    fun getHistory(): List<Pair<String, String>> {
        return history.toList()
    }
}

fun main() {

    // Crea una instancia de TaskQueue con una capacidad máxima de 5 tareas.
    val tareaQueue = TaskQueue(maxlen = 5)

    println("--- Simulación de Cola de Tareas ---")

    // Añade algunas tareas a la cola.
    tareaQueue.addTask("Tarea A")
    tareaQueue.addTask("Tarea B")
    tareaQueue.addTask("Tarea C")

    println("\n--- Estado Actual de la Cola ---")
    tareaQueue.getQueue().forEachIndexed { index, tarea ->
        println("Posición ${index + 1}: $tarea")
    }

    // Procesa algunas tareas y añade más.
    tareaQueue.processTask()
    tareaQueue.addTask("Tarea D")
    tareaQueue.processTask()
    tareaQueue.addTask("Tarea E")
    tareaQueue.addTask("Tarea F") // Esta tarea podría hacer que se elimine la más antigua si maxlen es 5.

    println("\n--- Estado Actual de la Cola Después de Más Operaciones ---")
    tareaQueue.getQueue().forEachIndexed { index, tarea ->
        println("Posición ${index + 1}: $tarea")
    }

    println("\n--- Historial de Operaciones de la Cola ---")
    tareaQueue.getHistory().forEach { (evento, tiempo) ->
        println("- [$tiempo] $evento")
    }

    println("--- Fin de la Simulación ---")
}

# Resultado en Consola:

**--- Simulación de Cola de Tareas ---**
- [2025-05-08 02:36:11] Tarea 'Tarea A' añadida a la cola.
- [2025-05-08 02:36:11] Tarea 'Tarea B' añadida a la cola.
- [2025-05-08 02:36:11] Tarea 'Tarea C' añadida a la cola.

**--- Estado Actual de la Cola ---**
- **Posición 1:** Tarea A
- **Posición 2:** Tarea B
- **Posición 3:** Tarea C
- [2025-05-08 02:36:11] Tarea 'Tarea A' procesada.
- [2025-05-08 02:36:11] Tarea 'Tarea D' añadida a la cola.
- [2025-05-08 02:36:11] Tarea 'Tarea B' procesada.
- [2025-05-08 02:36:11] Tarea 'Tarea E' añadida a la cola.
- [2025-05-08 02:36:11] Tarea 'Tarea F' añadida a la cola.

**--- Estado Actual de la Cola Después de Más Operaciones ---**
- **Posición 1:** Tarea C
- **Posición 2:** Tarea D
- **Posición 3:** Tarea E
- **Posición 4:** Tarea F

**--- Historial de Operaciones de la Cola ---**
- [2025-05-08 02:36:11] Añadida: Tarea F
- [2025-05-08 02:36:11] Añadida: Tarea E
- [2025-05-08 02:36:11] Procesada: Tarea B
- [2025-05-08 02:36:11] Añadida: Tarea D
- [2025-05-08 02:36:11] Procesada: Tarea A
- [2025-05-08 02:36:11] Añadida: Tarea C
- [2025-05-08 02:36:11] Añadida: Tarea B
- [2025-05-08 02:36:11] Añadida: Tarea A
**--- Fin de la Simulación ---**


# Explicación:

Este proyecto simula una cola de tareas utilizando la clase `LinkedList` de Java, que permite un manejo eficiente de elementos al principio y al final de la colección. Además de las operaciones básicas de una cola, se mantiene un historial de las acciones realizadas.

- **`TaskQueue` Class:** Define una clase para gestionar la cola de tareas y su historial.
 - **`queue: LinkedList<String>`:** Almacena las tareas pendientes. `LinkedList` se utiliza por su eficiencia en operaciones de adición y eliminación en los extremos.
 - **`history: LinkedList<Pair<String, String>>`:** Guarda un registro de las operaciones realizadas en la cola. Cada entrada es un par que contiene la descripción de la acción (e.g., "Añadida", "Procesada")
     y la marca de tiempo.
 - **`maxlen: Int?`:** Define una capacidad máxima opcional para la cola. Si se especifica y se alcanza, las nuevas tareas harán que se eliminen las más antiguas.
 - **`formatter: DateTimeFormatter`:** Formatea las marcas de tiempo para una mejor legibilidad.
 - **`addTask(task: String)`:** Añade una nueva tarea al final de la cola. Si la cola tiene una capacidad máxima y está llena, elimina la tarea más antigua. Registra la adición en el historial.
 - **`processTask(): String?`:** Remueve y retorna la primera tarea de la cola (FIFO). Registra el procesamiento en el historial. Retorna `null` si la cola está vacía.
 - **`getQueue(): List<String>`:** Retorna una copia inmutable del estado actual de la cola.
 - **`getHistory(): List<Pair<String, String>>`:** Retorna una copia inmutable del historial de operaciones.

- **`main()` Function:**
 - Crea una instancia de `TaskQueue` con una longitud máxima de 5.
 - Simula la adición y procesamiento de tareas, mostrando el estado de la cola y el historial en diferentes momentos.

Este ejemplo ilustra cómo implementar una estructura de cola con funcionalidades adicionales como un historial y una capacidad máxima utilizando la versatilidad de `LinkedList` en Kotlin. Es útil en escenarios donde se necesita gestionar tareas en orden y mantener un registro de su manipulación.

