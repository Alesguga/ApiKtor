# Tu Primera API con Ktor

## Requisitos:
- InteliJ IDEA
- Conocimiento básico de kotlin

Ktor, el framework asincrónico para crear microservicios o aplicaciones web y más, usando como lenguaje Kotlin.

## ¿Qué es Ktor?

Ktor es un marco de trabajo (framework) para construir servidores y clientes en Kotlin de manera conectada y fácil. Es moderno, rápido y asincrónico, lo que lo hace una herramienta perfecta para proyectos backend que requieren escalabilidad y eficiencia.

### Características de Ktor

- **Asíncrono desde el principio**: Diseñado para aprovechar las coroutines de Kotlin, lo que permite manejar miles de conexiones simultáneas de manera eficiente.
- **DSL Intuitivo**: Ktor utiliza un DSL (Lenguaje de Dominio Específico) para la definición de rutas y endpoints, haciendo el código más limpio y fácil de entender.
- **Extensible**: Viene con una gran cantidad de características listas para usar a través de plugins, pero también permite la personalización y creación de nuevos plugins según las necesidades del proyecto.
- **Multiplataforma**: No solo está pensado para el backend, sino que también puede utilizarse para crear clientes HTTP en multiplataforma (incluyendo Android e iOS).

## ¿Por Qué Probar Ktor?

- **Rendimiento**: Aprovecha la capacidad de manejo de coroutines de Kotlin para un rendimiento optimizado en operaciones de red.
- **Facilidad de Uso**: Gracias a su DSL, Ktor permite una curva de aprendizaje menos empinada y un desarrollo más ágil.
- **Flexibilidad**: Adaptable a cualquier tamaño de proyecto, desde microservicios hasta aplicaciones empresariales completas.

## Cómo Funciona Ktor

Ktor trabaja sobre la idea de módulos y características. Cada aplicación Ktor es configurada mediante un conjunto de módulos, los cuales definen cómo responder a diferentes solicitudes HTTP. Las características son piezas reutilizables de funcionalidad que se pueden agregar a estos módulos para extender su comportamiento, como la autenticación, serialización, manejo de sesiones y más.

## Como hacer tu primera API con Ktor

Accedemos a 
<a href="https://start.ktor.io/#/settings" target="_blank">Ktor Project generator</a>
- Le ponemos el nombre que queramos
- En adjust project settings seleccionamos
- Gradle kotlin
- En WebSite ponemos com.holamundo
- De engine usamos el predeterminado de KTOR que es Netty
- La configuración la vamos a albergar en un HOCON File
- No generamos Sample code ya que abajo dejare todo
- Pulsamos sobre plugins pero no seleccionamos ninguno
- Damos a generate y se nos genera un comprimido con el programa
- Creamos una carpeta donde vayamos a albergar todos nuestros trabajos con Ktor
- La abrimos desde inteliJ IDEA
- Cuando nos cargue todas las librerías accedemos a src/main/kotlin/el nombre del paquete/Application.kt
- Ahí dentro es donde configuraremos nuestra primera API

## Primera API
```kotlin

import io.ktor.server.application.*
import io.ktor.server.engine.*
import io.ktor.server.netty.*
import io.ktor.server.response.*
import io.ktor.server.routing.*

fun main() {
    embeddedServer(Netty, port = 8080) {
        routing {
            get("/") {
                call.respondText("¡Hola, mundo!")
            }
            //Esta nos llevara a un dominio de preferencia podeis cambiar al que querais
            get("/guti"){
                call.respondRedirect("https://gutigut.com/")
            }
        }
    }.start(wait = true)
}
```
