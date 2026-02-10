
# 🧩 Unidad 1 — Procesos y su gestión

## 1. Conceptos básicos
- **Programa:** conjunto estático de instrucciones y datos almacenado en un fichero binario.
- **Proceso:** entidad dinámica que se crea al cargar un programa en memoria principal para su ejecución.
- **Servicios:** procesos que se ejecutan en segundo plano (background), sin interfaz de usuario, ofreciendo funcionalidades a otros procesos o usuarios.

## 2. Ejecución y concurrencia
- Un sistema operativo puede ejecutar **varios procesos aparentemente de forma simultánea** gracias a la **multiprogramación** (cambio rápido entre procesos) o **multitarea** (reparto del procesador entre tareas).
- Aunque exista un solo procesador, el sistema operativo alterna entre procesos dando la sensación de ejecución paralela: esto es **concurrencia**.
- En sistemas con varios procesadores, se puede hablar de **paralelismo real**.

## 3. Estados de un proceso
Durante su ciclo de vida, un proceso pasa por distintos **estados**:
- **Listo:** preparado para ejecutarse.
- **Ejecución:** en uso del procesador.
- **Bloqueado:** esperando un evento (E/S u otro recurso).
- **Suspendido o detenido:** pausado temporalmente.
- **Finalizado:** ha terminado su ejecución.

Los cambios de estado se gestionan mediante **planificación**:
- **A corto plazo:** decide qué proceso ocupa la CPU.
- **A medio y largo plazo:** controla el grado de multiprogramación y la carga del sistema.

Cada cambio de proceso implica un **cambio de contexto**, donde el sistema guarda la información del proceso saliente y restaura la del entrante.

## 4. Creación y jerarquía de procesos
- El **proceso padre** crea procesos **hijos** mediante la operación `create`.
- El hijo puede ser destruido con `destroy` o esperar a que finalice con `wait`.
- De esta forma, el sistema forma un **árbol de procesos** (padre-hijo).

Cada proceso tiene un **PID** (identificador único) y una interfaz con el sistema:
- **Entrada estándar (stdin):** recibe datos.
- **Salida estándar (stdout):** envía resultados.
- **Salida de error (stderr):** mensajes de error.

## 5. Gestión y comunicación entre procesos
- La comunicación entre procesos (IPC) puede ser **local** (mismo sistema) o **remota** (a través de red y protocolos).
- En Java, la clase **`Process`** permite gestionar procesos.
- Se crean mediante **`Runtime`** o **`ProcessBuilder`**, que facilitan la redirección de entradas y salidas.
- La clase **`Process`** usa **streams** para enviar o leer datos desde el proceso.

## 6. Planificación y control
- El **planificador (scheduler)** administra los procesos listos para ejecución.
- Puede usar distintas políticas:
  - **Apropiativa:** interrumpe procesos para asignar CPU a otros.
  - **Cooperativa:** los procesos ceden el control voluntariamente.
- La **prioridad** de un proceso afecta el orden en el que recibe tiempo de CPU.

## 7. Características del sistema operativo
- Cada sistema operativo implementa sus propias estrategias de gestión de procesos.
- En entornos como la **JVM de Java**, la gestión se abstrae del usuario, pero se pueden crear y controlar procesos mediante las clases de la API estándar.

---

## 🧠 Conclusión general
La Unidad 1 enseña cómo el sistema operativo gestiona los **procesos**, los **cambia de estado**, y permite que varios se ejecuten simultáneamente mediante **planificación** y **multiprogramación**.  
También introduce la **creación y comunicación de procesos** desde Java, usando clases como `Process` y `ProcessBuilder`, lo que permite integrar el control de procesos del sistema operativo dentro de las aplicaciones.
