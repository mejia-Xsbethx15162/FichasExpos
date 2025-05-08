Estructura #7

# LOOPERS

---

## 1. Describa el por qué y para qué se utiliza

En Kotlin (y en el contexto de desarrollo en Android, donde Kotlin es un lenguaje primario), los Loopers se utilizan principalmente dentro del sistema de mensajería 
de Android para permitir que un hilo que no es el hilo principal (UI thread) pueda recibir y procesar mensajes o Runnables de forma asíncrona.

**¿Para qué se utiliza un Looper?**

El propósito fundamental de un Looper es gestionar una cola de mensajes (MessageQueue) para un hilo específico. Esto permite que el hilo realice tareas en respuesta a esos mensajes de manera ordenada y 
sin bloquear el hilo principal (la interfaz de usuario).

**Aquí están los casos de uso principales:**

- **Ejecución de tareas en segundo plano con comunicación con el hilo principal:** Un Looper permite crear hilos de trabajo (background threads) que pueden recibir instrucciones (en forma de mensajes o Runnables)
  y realizar tareas largas o bloqueantes sin congelar la interfaz de usuario. Una vez completadas o durante su ejecución, estos hilos pueden enviar mensajes de vuelta al hilo principal
  (que también tiene un Looper) para actualizar la UI de forma segura.
- **Implementación de manejadores (Handlers):** Los Handlers son clases que se asocian a un Looper (generalmente el del hilo en el que se crean). Permiten enviar y procesar Messages o Runnables
  en la MessageQueue del Looper asociado. Esto simplifica la comunicación entre diferentes hilos.
- **Manejo de eventos asíncronos dentro de un hilo:** Un hilo puede tener su propio Looper para gestionar eventos internos de manera asíncrona. Por ejemplo, un servicio en segundo plano podría usar
 un Looper para procesar solicitudes entrantes de forma secuencial.

**¿Por qué se utiliza un Looper?**

**La necesidad de Loopers surge principalmente por las siguientes razones:**

- **Evitar el bloqueo del hilo principal (UI Thread):** En Android, todas las operaciones que modifican la interfaz de usuario deben realizarse en el hilo principal. Si se realizan tareas largas o bloqueantes directamente 
  en el hilo principal, la aplicación se congelará y la experiencia del usuario será terrible (la famosa "Application Not Responding" o ANR). Los Loopers permiten delegar estas tareas a hilos en segundo plano.
- **Comunicación segura entre hilos:** Los Loopers, junto con Handlers y MessageQueues, proporcionan un mecanismo seguro y ordenado para la comunicación entre diferentes hilos. En lugar de que los hilos accedan 
  directamente a los datos de otros hilos (lo que puede llevar a condiciones de carrera y errores), se envían mensajes a través de la MessageQueue del Looper del hilo de destino. Este hilo procesa los mensajes de forma 
  secuencial, evitando problemas de concurrencia.
- **Modelo de programación basado en eventos:** El uso de Loopers facilita la implementación de un modelo de programación basado en eventos dentro de un hilo. El hilo con un Looper espera en un bucle a que lleguen 
  mensajes a su MessageQueue y luego los procesa. Esto permite una arquitectura más limpia y reactiva.
- **Integración con el sistema Android:** El propio sistema operativo Android utiliza Loopers extensamente. El hilo principal de cada aplicación tiene un Looper asociado (Looper.getMainLooper()). Componentes del sistema 
  como Activity, Service, etc., utilizan Handlers que se ejecutan en el Looper del hilo principal para manejar eventos del ciclo de vida, eventos de usuario, etc.

**Tipos:**

- **for:** El "Visitante Sistemático": Recorre cada rincón de tus datos (rangos, listas), actuando sobre cada elemento de manera predecible.
- **while:** El "Portero Condicional": Ejecuta su bloque solo mientras una regla se cumpla, deteniéndose al instante en que falla.
- **do-while:** El "Ejecutor Incondicional (Inicialmente)": Realiza su acción al menos una vez, luego repite solo si se le permite.

**El Rol de los Bucles (Más Breve):**

- **Automatización Directa:** Simplifican tareas repetitivas, evitando la escritura manual extensa.
- **Exploración de Datos:** Permiten moverse a través de colecciones para procesar o encontrar información.
- **Ritmo Programático:** Establecen patrones de repetición para procesos iterativos o basados en condiciones.

---

## 2. Genere un ejemplo internamente en el recuadro

- Utilice un editor de código para lograrlo.
- [🔗 Link del Código](https://pl.kotl.in/4PY7GKyrV) <!-- Aquí puedes reemplazar # por el enlace real de tu archivo en GitHub -->

---

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](#)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/c8d0daf75ce94553b2380824e8d6ef2dc935b206/LoopersBucles/Loopers.png)

---

# Escribe una nota del cómo funciona la estructura

fun main() {

    val objetivo = 20
    var suma = 0
    var intentos = 0

    println("--- Sumando números hasta alcanzar o superar $objetivo ---")

    // Bucle while para continuar sumando hasta alcanzar el objetivo
    while (suma < objetivo) {
        intentos++
        println("\nIntento $intentos:")
        val numerosASumar = mutableListOf<Int>()
        val cantidadNumeros = (1..4).random() // Sumar entre 1 y 4 números en cada intento

        // Bucle for para generar y sumar una cantidad variable de números
        for (i in 1..cantidadNumeros) {
            val numeroAleatorio = (1..10).random()
            numerosASumar.add(numeroAleatorio)
            suma += numeroAleatorio
            print("+ $numeroAleatorio ")
        }

        println("= $suma")

        if (suma >= objetivo) {
            println("\n¡Objetivo alcanzado ($suma) en $intentos intentos!")
        } else {
            println("La suma actual ($suma) es menor que el objetivo ($objetivo).")
        }
    }

    println("--- Fin de la suma ---")
}

# Resultado en Consola:

**--- Sumando números hasta alcanzar o superar 20 ---**

- **Intento 1:**
  + 1 + 4 + 10 + 5 = 20

  ¡Objetivo alcanzado (20) en 1 intentos!
  
**--- Fin de la suma ---**


# Explicación:

Este código utiliza un bucle `while` para controlar el proceso general de sumar números hasta que la `suma` alcance o supere un `objetivo` (en este caso, 20). Dentro de cada iteración del `while`:

- Se incrementa el contador de `intentos`.
- Se utiliza un bucle `for` para generar una cantidad aleatoria de números (entre 1 y 4) y sumarlos a la variable `suma`.
- Se imprime la operación de suma realizada en ese intento.
- Se verifica si se ha alcanzado el `objetivo`. Si es así, se imprime un mensaje de éxito y el bucle `while` termina debido a la condición (`suma < objetivo`) que ahora es falsa. Si no, se indica que la suma actual es 
  menor que el objetivo.

Este ejemplo demuestra cómo se pueden anidar bucles (`while` conteniendo un `for`) para realizar tareas más complejas y cómo las condiciones de los bucles controlan el flujo del programa. 
No debería generar un `OutOfMemoryError` con valores razonables para el `objetivo` y los rangos de números aleatorios.
