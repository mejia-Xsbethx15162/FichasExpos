Estructura #11

# POO

---

## 1. Describa el por qué y para qué se utiliza

La Programación Orientada a Objetos (POO) es un paradigma de programación que se centra en la organización del software alrededor de "objetos", que son instancias de "clases". Kotlin adopta plenamente los principios de la POO, proporcionando las herramientas necesarias para construir sistemas robustos, modulares y extensibles. A continuación, se describe en detalle cada uno de los pilares fundamentales de la POO en Kotlin: Encapsulamiento, Herencia, Abstracción y Polimorfismo, junto con ejemplos concretos.

**Encapsulamiento:**

El encapsulamiento es el principio de agrupar los datos (propiedades o atributos) y el código que opera sobre esos datos (métodos o funciones) dentro de una misma unidad, la clase. Además, implica controlar el acceso a 
los detalles internos del objeto, ocultando la implementación y exponiendo solo una interfaz pública para interactuar con él.

**¿Por Qué Encapsular?**

- **Protección de Datos:** Evita la manipulación directa e incorrecta de los datos internos de un objeto desde fuera de la clase, manteniendo la integridad del estado del objeto.
- **Ocultación de la Implementación:** Permite cambiar la implementación interna de una clase sin afectar el código que la utiliza, siempre y cuando la interfaz pública se mantenga consistente. Esto facilita el 
  mantenimiento y la refactorización.
- **Modularidad:** Promueve la creación de módulos de código autocontenidos y bien definidos, lo que facilita la comprensión y el desarrollo.
  
**¿Cómo se logra en Kotlin?**

Kotlin utiliza modificadores de visibilidad para controlar el acceso a las propiedades y métodos de una clase:

- **public (por defecto):** Visible en todas partes.
- **internal:** Visible dentro del mismo módulo.
- **protected:** Visible dentro de la clase y sus subclases.
- **private:** Visible solo dentro de la misma clase.
  
**Ejemplo de Encapsulamiento:**

//class Persona(private val nombre: String, private var edad: Int) {

    // Propiedad pública (solo lectura a través de getter implícito)
    val nombreCompleto: String get() = nombre

    // Método público para obtener la edad (control de acceso)
    fun obtenerEdad(): Int {
        return edad
    }

    // Método público para actualizar la edad (con lógica de validación)
    fun actualizarEdad(nuevaEdad: Int) {
        if (nuevaEdad >= 0) {
            edad = nuevaEdad
            println("Edad de $nombre actualizada a $edad.")
        } else {
            println("La edad no puede ser negativa.")
        }
    }

    // Método privado (solo accesible dentro de la clase Persona)
    private fun esMayorDeEdad(): Boolean {
        return edad >= 18
    }

    fun mostrarEstado() {
        println("$nombre tiene $edad años. ¿Es mayor de edad? ${esMayorDeEdad()}.")
    }
}

fun main() {

    val persona = Persona("Alice", 25)
    println("Nombre: ${persona.nombreCompleto}")
    println("Edad: ${persona.obtenerEdad()}")
    persona.actualizarEdad(26)
    persona.actualizarEdad(-5)

    // persona.nombre // Error: 'nombre' es privado
    // persona.edad // Error: 'edad' es privado
    // persona.esMayorDeEdad() // Error: 'esMayorDeEdad' es privado

    persona.mostrarEstado()
}

# Resultado en Consola:
- Nombre: Alice
- Edad: 25
- Edad de Alice actualizada a 26.
- La edad no puede ser negativa.
- Alice tiene 26 años. ¿Es mayor de edad? true.

**Herencia:**

La herencia es un mecanismo que permite a una clase (subclase o clase derivada) heredar propiedades y métodos de otra clase (superclase o clase base). Esto fomenta la reutilización de código y la creación de jerarquías de 
clases que representan relaciones "es-un-tipo-de".

**¿Por Qué Herencia?**

- **Reutilización de Código:** Evita la duplicación de código al permitir que las subclases hereden funcionalidades comunes de la superclase.
- **Extensibilidad:** Permite extender el comportamiento de una clase base añadiendo nuevas propiedades y métodos en las subclases.
- **Mantenibilidad:** Los cambios en la clase base se reflejan automáticamente en las subclases (a menos que se sobrescriban los miembros).
- **Polimorfismo (se relaciona directamente):** Facilita el polimorfismo al permitir tratar objetos de diferentes subclases de manera uniforme a través de una referencia a su superclase.

**¿Cómo se logra en Kotlin?**

- La herencia se declara utilizando el operador : seguido del nombre de la superclase en la definición de la subclase.
- Las clases en Kotlin son final por defecto (no se pueden heredar). Para permitir la herencia, la superclase debe marcarse como open.
- Los métodos y propiedades que se pueden sobrescribir en las subclases también deben marcarse como open en la superclase.
- La sobrescritura en la subclase se indica con la palabra clave override.

**Ejemplo de Herencia:**

// open class Animal(val nombre: String) {

    open fun hacerSonido() {
        println("$nombre hace un sonido genérico.")
    }
}

class Perro(nombre: String, val raza: String) : Animal(nombre) {
    override fun hacerSonido() {
        println("$nombre ($raza) dice: ¡Guau guau!")
    }

    fun ladrar() {
        println("$nombre ($raza) está ladrando.")
    }
}

class Gato(nombre: String, val color: String) : Animal(nombre) {
    override fun hacerSonido() {
        println("$nombre ($color) dice: ¡Miau miau!")
    }

    fun ronronear() {
        println("$nombre ($color) está ronroneando.")
    }
}

fun main() {

    val miPerro = Perro("Buddy", "Golden Retriever")
    miPerro.hacerSonido()
    miPerro.ladrar()

    val miGato = Gato("Pelusa", "Blanco")
    miGato.hacerSonido()
    miGato.ronronear()

    val animalGenerico: Animal = Perro("Max", "Pastor Alemán") // Upcasting
    animalGenerico.hacerSonido() // Se llama a la versión de Perro
}

# Resultado en Consola:
- Buddy (Golden Retriever) dice: ¡Guau guau!
- Buddy (Golden Retriever) está ladrando.
- Pelusa (Blanco) dice: ¡Miau miau!
- Pelusa (Blanco) está ronroneando.
- Max (Pastor Alemán) dice: ¡Guau guau!

**Abstracción:**

La abstracción es el proceso de ocultar los detalles de implementación complejos y mostrar solo la información esencial al usuario. Se centra en el "qué" hace un objeto en lugar del "cómo" lo hace.

**¿Por Qué Abstracción?**

- **Simplicidad:** Reduce la complejidad al ocultar los detalles internos, facilitando el uso de los objetos.
- **Flexibilidad:** Permite cambiar la implementación interna sin afectar la interfaz externa.
- **Mantenibilidad:** Los cambios internos son menos propensos a romper el código que utiliza la abstracción.
  
**¿Cómo se logra en Kotlin?**

- **Clases Abstractas:** Se declaran con la palabra clave abstract. No se pueden instanciar directamente y pueden contener métodos abstractos (sin implementación) y métodos concretos (con implementación). Las subclases 
  deben implementar los métodos abstractos.
- **Interfaces:** Definen un contrato (un conjunto de métodos abstractos) que las clases pueden implementar. Una clase puede implementar múltiples interfaces.

**Ejemplo de Abstracción (Clase Abstracta):**

// abstract class Figura(val color: String) {

    abstract fun calcularArea(): Double
    abstract fun dibujar()

    fun mostrarColor() {
        println("Color de la figura: $color")
    }
}

class Circulo(color: String, val radio: Double) : Figura(color) {
    override fun calcularArea(): Double {
        return Math.PI * radio * radio
    }

    override fun dibujar() {
        println("Dibujando un círculo de radio $radio y color $color.")
    }
}

class Rectangulo(color: String, val base: Double, val altura: Double) : Figura(color) {
    override fun calcularArea(): Double {
        return base * altura
    }

    override fun dibujar() {
        println("Dibujando un rectángulo de base $base, altura $altura y color $color.")
    }
}

fun main() {

    // val figura = Figura("Rojo") // Error: No se puede instanciar una clase abstracta

    val circulo = Circulo("Azul", 5.0)
    circulo.mostrarColor()
    circulo.dibujar()
    println("Área del círculo: ${"%.2f".format(circulo.calcularArea())}")

    val rectangulo = Rectangulo("Verde", 4.0, 6.0)
    rectangulo.mostrarColor()
    rectangulo.dibujar()
    println("Área del rectángulo: ${"%.2f".format(rectangulo.calcularArea())}")

    val figuras: List<Figura> = listOf(circulo, rectangulo)
    figuras.forEach { it.dibujar() } // Polimorfismo en acción
}

# Resultado en Consola:
- Color de la figura: Azul
- Dibujando un círculo de radio 5.0 y color Azul.
- Área del círculo: 78.54
- Color de la figura: Verde
- Dibujando un rectángulo de base 4.0, altura 6.0 y color Verde.
- Área del rectángulo: 24.00
- Dibujando un círculo de radio 5.0 y color Azul.
- Dibujando un rectángulo de base 4.0, altura 6.0 y color Verde.

**Polimorfismo:**

El polimorfismo (que significa "muchas formas") es la capacidad de que objetos de diferentes clases respondan a la misma invocación de método de manera diferente. Permite tratar objetos de diferentes tipos de forma uniforme a través de una interfaz común (generalmente una superclase o una interfaz).

**¿Por Qué Polimorfismo?**

- **Flexibilidad:** Permite escribir código más genérico que puede trabajar con objetos de diferentes tipos.
- **Extensibilidad:** Facilita la adición de nuevas clases sin necesidad de modificar significativamente el código existente que utiliza la interfaz común.
- **Reutilización de Código:** Permite escribir algoritmos que operan sobre una variedad de objetos a través de su interfaz común.

**¿Cómo se logra en Kotlin?**

- **Sobrescritura de Métodos (Herencia):** Las subclases pueden proporcionar su propia implementación de métodos heredados de la superclase (override).
- **Interfaces:** Múltiples clases pueden implementar la misma interfaz, proporcionando sus propias implementaciones de los métodos definidos en la interfaz.
- **Upcasting y Downcasting:** Un objeto de una subclase puede ser tratado como un objeto de su superclase (upcasting). Si es necesario acceder a miembros específicos de la subclase, se puede realizar un downcasting
  (con precaución y verificación de tipo).
  
**Ejemplo de Polimorfismo (con Herencia y Clases Abstractas):**

El ejemplo de la clase abstracta Figura también ilustra el polimorfismo. La lista figuras contiene objetos de tipo Circulo y Rectangulo, pero cuando se llama al método dibujar() en cada elemento, se invoca la implementación específica de la subclase.

**Ejemplo de Polimorfismo (con Interfaces):**

// interface Sonido {

    fun emitirSonido()
}

class PerroSonido : Sonido {
    override fun emitirSonido() {
        println("¡Guau guau!")
    }
}

class GatoSonido : Sonido {
    override fun emitirSonido() {
        println("¡Miau miau!")
    }
}

fun hacerRuido(animalSonido: Sonido) {
    animalSonido.emitirSonido()
}

fun main() {

    val perroSonido = PerroSonido()
    val gatoSonido = GatoSonido()

    hacerRuido(perroSonido) // Se llama a la implementación de PerroSonido
    hacerRuido(gatoSonido)   // Se llama a la implementación de GatoSonido

    val listaDeSonidos: List<Sonido> = listOf(perroSonido, gatoSonido)
    listaDeSonidos.forEach { it.emitirSonido() } // Polimorfismo en la colección
}

# Resultado en Consola:
- ¡Guau guau!
- ¡Miau miau!
- ¡Guau guau!
- ¡Miau miau!

---

## 2. Genere un ejemplo internamente en el recuadro

- Utilice un editor de código para lograrlo.
- [🔗 Link del Código](https://pl.kotl.in/sSVVjpDp8) <!-- Aquí puedes reemplazar # por el enlace real de tu archivo en GitHub -->

---

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](#)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/c8c08c09f5872d40ecb75a0eabc13190ee2b2ba4/POO/POO.png)

---

# Escribe una nota del cómo funciona la estructura

// interface Notificador {

    fun enviarNotificacion(mensaje: String)
}

class NotificadorEmail : Notificador {
    override fun enviarNotificacion(mensaje: String) {
        println("Enviando correo electrónico: $mensaje")
    }
}

class NotificadorSMS : Notificador {
    override fun enviarNotificacion(mensaje: String) {
        println("Enviando SMS: $mensaje")
    }
}

class NotificadorPush : Notificador {
    override fun enviarNotificacion(mensaje: String) {
        println("Enviando notificación push: $mensaje")
    }
}

fun main() {

    val emailNotificador = NotificadorEmail()
    val smsNotificador = NotificadorSMS()
    val pushNotificador = NotificadorPush()

    enviarNotificacion(emailNotificador, "¡Nueva actualización disponible!")
    enviarNotificacion(smsNotificador, "Recordatorio: cita mañana.")
    enviarNotificacion(pushNotificador, "Tienes un nuevo mensaje.")
    println()

    val notificadores: List<Notificador> = listOf(emailNotificador, smsNotificador, pushNotificador)
    notificadores.forEach { it.enviarNotificacion("Notificación genérica.") } // Polimorfismo
}

fun enviarNotificacion(notificador: Notificador, mensaje: String) {
    notificador.enviarNotificacion(mensaje)
}

# Resultado en Consola:
- **Enviando correo electrónico:** ¡Nueva actualización disponible!
- **Enviando SMS:** Recordatorio: cita mañana.
- **Enviando notificación push:** Tienes un nuevo mensaje.

- **Enviando correo electrónico:** Notificación genérica.
- **Enviando SMS:** Notificación genérica.
- **Enviando notificación push:** Notificación genérica.

# Explicación:
- **Abstracción (Interfaz):** La interfaz `Notificador` define un contrato (`enviarNotificacion`) que deben implementar todas las clases que deseen actuar como notificadores. Esto abstrae la forma en que
  se envía una notificación.
- **Polimorfismo:** La función `enviarNotificacion(notificador: Notificador, mensaje: String)` puede aceptar cualquier objeto que implemente la interfaz `Notificador`. Al llamar a 
 `notificador.enviarNotificacion(mensaje)`, se ejecuta la implementación específica de la clase del objeto pasado como argumento. La lista `notificadores` también demuestra polimorfismo al iterar sobre diferentes tipos
  de notificadores y llamar al mismo método con comportamientos distintos.
