Estructura #2

# Operadores Matematicos Logicos:

---

## 1. Describa el por qué y para qué se utiliza

Los operadores matemáticos lógicos son fundamentales en la programación y en Kotlin para realizar
operaciones y comparaciones.

# Operadores:

- **Suma (+)**
- **Resta (-)**
- **Multiplicación (*)**
- **División (/)**
- **Modulo (%)**

# Operadores de Comparación

- **Igual a (==)**
- **Mayor que (>)**
- **Menor que (<)**
- **Diferente de (!=)**
- **Mayor o Igual que (>=)**
- **Menor o Igual que (<=)**

# Operadores de Asignación

- **(+=)**
- **(-=)**
- **(*=)**
- **(/=)**
- **(%=)**

# Operadores Lógicos

- **And (&&)**
- **Not (!)**
- **Or (||)**

---

## 2. Genere un ejemplo internamente en el recuadro.

- Utilice un editor de código para lograrlo.
  [🔗 Link del Código](https://pl.kotl.in/mywCjRVjV)

## 3. En el listado compartido busque el algoritmo que corresponda y explíquelo paso a paso

- Genere el link del audio y el link del GitHub.
  
- [🔗 Link del audio](#)
- [🔗 Link del código probado por US y Guardado en GitHub](https://github.com/mejia-Xsbethx15162/FichasExpos/blob/6db4fd3776e313f94eecd3e12e7f09b559c94157/Variables/Variables.jpeg)

---

# Escribe una nota del cómo funciona la estructura

// fun main() {

    // Variables mutables (pueden cambiar de valor)
    var ciudad: String = "Madrid"
    var temperatura: Int = 22
    var velocidadViento: Double = 15.5
    var lloviendo: Boolean = false

    // Variables inmutables (no pueden cambiar de valor)
    val continente: String = "Europa"
    val gravedad: Float = 9.81f

    // Imprimir los valores
    println("Ciudad: $ciudad")
    println("Temperatura: $temperatura °C")
    println("Velocidad del viento: $velocidadViento km/h")
    println("¿Está lloviendo?: $lloviendo")
    println("Continente: $continente")
    println("Gravedad terrestre: $gravedad m/s²")

    // Modificando variables mutables
    ciudad = "Barcelona"
    temperatura = 18

    println("Nueva ciudad: $ciudad")
    println("Nueva temperatura: $temperatura °C")
// }

# Resultado en Consola:

Ciudad: Madrid
Temperatura: 22 °C
Velocidad del viento: 15.5 km/h
¿Está lloviendo?: false
Continente: Europa
Gravedad terrestre: 9.81 m/s²
Nueva ciudad: Barcelona
Nueva temperatura: 18 °C


# Explicación:

- **Variables mutables (var)**: Son aquellas que pueden cambiar de valor a lo largo de la ejecución del programa, como ciudad y temperatura.
- **Variables inmutables (val)**: Una vez asignado un valor, no se puede cambiar. continente y gravedad permanecen constantes.
- Se utilizan println para mostrar el valor de cada variable en consola.
- Se demuestra cómo es posible actualizar el valor de las variables mutables posteriormente.

