Estructura #10

# Class

---

## 1. Describa el por qué y para qué se utiliza

Las class en Kotlin (y en la programación orientada a objetos en general) son bloques de construcción fundamentales que se utilizan por razones clave y para propósitos esenciales en el desarrollo de software.

**¿Por Qué usar class?**

- **Modelar el Mundo:** Representan entidades con características y acciones. **¿Para qué?** Programas intuitivos.
- **Encapsular:** Juntan datos y código, ocultando detalles. **¿Para qué?** Proteger datos, facilitar cambios.
- **Abstraer:** Enfocarse en lo esencial, ignorar lo complejo. **¿Para qué?** Simplificar uso.
- **Reutilizar:** Crear múltiples objetos con la misma estructura. **¿Para qué?** Menos código.
- **Heredar:** Compartir y extender funcionalidades entre clases. **¿Para qué?** Organizar y evitar repetición.
- **Polimorfismo:** Objetos diferentes responden similarmente. **¿Para qué?** Código flexible y adaptable.

**¿Para Qué usar class?**

- Crear tipos de datos propios.
- Organizar código.
- Aplicar Programación Orientada a Objetos (POO).
- Construir librerías y frameworks.
- Desarrollar aplicaciones complejas.
- Interactuar con otros sistemas OO.

---

## 2. Genere un ejemplo internamente en el recuadro

- Utilice un editor de código para lograrlo.
- [🔗 Link del Código](https://pl.kotl.in/tGzPWv1pR) <!-- Aquí puedes reemplazar # por el enlace real de tu archivo en GitHub -->

---

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](https://github.com/mejia-Xsbethx15162/FichasExpos/raw/refs/heads/main/Class/Class.ogg)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/d03fbedea6aae556196e156a241ddbdeb96fd433/Class/Class.png)

---

# Escribe una nota del cómo funciona la estructura

// open class Animal(val nombre: String) {

    open fun hacerSonido() {
        println("$nombre hace un sonido genérico.")
    }
}

class Perro(nombre: String) : Animal(nombre) {
    override fun hacerSonido() {
        println("$nombre dice: ¡Guau guau!")
    }

    fun ladrar() {
        println("$nombre está ladrando.")
    }
}

class Gato(nombre: String) : Animal(nombre) {
    override fun hacerSonido() {
        println("$nombre dice: ¡Miau miau!")
    }

    fun ronronear() {
        println("$nombre está ronroneando.")
    }
}

fun main() {

    val miPerro = Perro("Buddy")
    miPerro.hacerSonido() // Polimorfismo
    miPerro.ladrar()

    val miGato = Gato("Pelusa")
    miGato.hacerSonido() // Polimorfismo
    miGato.ronronear()

    val animalGenerico: Animal = Perro("Max") // Upcasting
    animalGenerico.hacerSonido() // Se llama a la versión de Perro

    // animalGenerico.ladrar() // Esto daría un error de compilación, Animal no tiene ladrar
}

# Resultado en Consola:

- **Buddy dice:** ¡Guau guau!
- Buddy está ladrando.
- **Pelusa dice:** ¡Miau miau!
- Pelusa está ronroneando.
- **Max dice:** ¡Guau guau!


# Explicación:

- Se define una clase base `Animal` con una propiedad `nombre` y una función `hacerSonido` (marcada como `open` para permitir la sobreescritura).
- Las clases `Perro` y `Gato` heredan de `Animal` usando la sintaxis `: Animal(nombre)`.
- La función `hacerSonido` se **sobreescribe** (`override`) en las subclases para proporcionar un comportamiento específico para cada tipo de animal (polimorfismo).
- Cada subclase también introduce comportamientos adicionales específicos (`ladrar` para `Perro`, `ronronear` para `Gato`).
- Se demuestra el **upcasting**, donde una instancia de una subclase se asigna a una variable del tipo de la superclase. En este caso, solo se pueden acceder a los miembros definidos en la superclase (`Animal`).
