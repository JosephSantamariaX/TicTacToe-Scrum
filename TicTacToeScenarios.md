# Tic Tac Toe – Escenarios BDD

Este documento define escenarios de comportamiento para el juego Tic Tac Toe utilizando el formato **Given–When–Then** (Dado–Cuando–Entonces).  
Los escenarios están basados en las historias de usuario definidas para el proyecto.

---

## 1. Inicio del Juego

### Escenario 1.1: Iniciar una nueva partida como jugador X
**Given** que el usuario está en la pantalla inicial del juego  
**When** selecciona jugar como "X" y presiona el botón "Iniciar partida"  
**Then** se debe mostrar un tablero vacío de 3x3  
**And** debe indicarse visualmente que es el turno del jugador "X".

### Escenario 1.2: Iniciar una nueva partida como jugador O
**Given** que el usuario está en la pantalla inicial del juego  
**When** selecciona jugar como "O" y presiona el botón "Iniciar partida"  
**Then** se debe mostrar un tablero vacío de 3x3  
**And** debe indicarse visualmente que es el turno del jugador "O".

---

## 2. Realizar un Movimiento

### Escenario 2.1: Marcar una casilla vacía
**Given** que la partida está en progreso  
**And** es el turno del jugador actual  
**And** hay al menos una casilla vacía en el tablero  
**When** el jugador hace clic en una casilla vacía  
**Then** la casilla debe mostrar la marca del jugador actual ("X" u "O")  
**And** ya no debe ser posible volver a hacer clic en esa casilla.

### Escenario 2.2: Intentar marcar una casilla ocupada
**Given** que una casilla ya tiene una marca ("X" u "O")  
**When** el jugador intenta hacer clic de nuevo en esa casilla  
**Then** el juego no debe cambiar la marca existente  
**And** no debe afectar el turno actual ni el estado de la partida.

### Escenario 2.3: Cambiar de turno después de una jugada válida
**Given** que es el turno del jugador "X"  
**And** el tablero tiene al menos una casilla vacía  
**When** el jugador "X" marca una casilla válida  
**Then** el juego debe cambiar el turno al jugador "O"  
**And** debe actualizarse el indicador visual del turno.

---

## 3. Determinación de Ganador y Empate

### Escenario 3.1: Ganar por fila
**Given** que el jugador "X" ya tiene dos casillas marcadas en la misma fila  
**And** hay una tercera casilla vacía en esa fila  
**When** el jugador "X" marca la tercera casilla en esa fila  
**Then** el juego debe detectar que el jugador "X" ha ganado  
**And** debe mostrar un mensaje indicando que "X" es el ganador  
**And** debe evitar que se sigan realizando jugadas.

### Escenario 3.2: Ganar por columna
**Given** que el jugador "O" ya tiene dos casillas marcadas en la misma columna  
**And** hay una tercera casilla vacía en esa columna  
**When** el jugador "O" marca la tercera casilla en esa columna  
**Then** el juego debe detectar que el jugador "O" ha ganado  
**And** debe mostrar un mensaje indicando que "O" es el ganador  
**And** debe evitar que se sigan realizando jugadas.

### Escenario 3.3: Ganar por diagonal
**Given** que el jugador "X" ya tiene dos casillas marcadas en una diagonal  
**And** hay una tercera casilla vacía en esa diagonal  
**When** el jugador "X" marca la tercera casilla en esa diagonal  
**Then** el juego debe detectar que el jugador "X" ha ganado  
**And** debe mostrar un mensaje indicando que "X" es el ganador  
**And** debe evitar que se sigan realizando jugadas.

### Escenario 3.4: Empate sin ganador
**Given** que todas las casillas del tablero están llenas  
**And** no existe ninguna fila, columna o diagonal con tres marcas iguales  
**When** el jugador intenta realizar una nueva jugada  
**Then** el juego debe indicar que la partida ha terminado en empate  
**And** no debe permitir más movimientos.

---

## 4. Reiniciar el Juego

### Escenario 4.1: Reiniciar la partida desde el tablero
**Given** que una partida ha terminado en victoria o empate  
**When** el usuario presiona el botón "Reiniciar"  
**Then** el tablero debe restablecerse a un estado vacío de 3x3  
**And** no debe haber marcas previas en ninguna casilla  
**And** el juego debe permitir nuevamente seleccionar quién juega como "X" y "O" o mantener la configuración definida.

### Escenario 4.2: Reiniciar durante una partida en progreso
**Given** que hay una partida en progreso (no ha terminado)  
**When** el usuario presiona el botón "Reiniciar"  
**Then** el tablero debe limpiarse completamente  
**And** el estado del juego debe volver a su estado inicial  
**And** el turno debe reiniciarse según la configuración seleccionada.

---

## 5. Interfaz de Usuario Intuitiva

### Escenario 5.1: Visualización clara del tablero
**Given** que el usuario ha iniciado el juego  
**When** se muestra el tablero  
**Then** las 9 casillas deben estar claramente delimitadas  
**And** deben ser fácilmente identificables como clicables o seleccionables.

### Escenario 5.2: Indicador de turno visible
**Given** que el juego está en progreso  
**When** cambia el turno de un jugador a otro  
**Then** debe actualizarse un indicador visible mostrando de quién es el turno actual  
**And** el jugador debe poder identificar fácilmente cuándo le toca jugar.

### Escenario 5.3: Mensajes claros de estado del juego
**Given** que la partida ha terminado en victoria o empate  
**When** el juego muestra el resultado  
**Then** el mensaje debe indicar claramente si hubo un ganador o si fue empate  
**And** el mensaje debe ser lo suficientemente visible para que el usuario no tenga dudas del resultado.

---

## 6. Modo Multijugador Local

### Escenario 6.1: Alternar turnos entre dos jugadores en el mismo dispositivo
**Given** que se ha iniciado una partida en modo multijugador local  
**When** el jugador 1 realiza una jugada válida  
**Then** el turno debe pasar al jugador 2  
**And** el indicador de turno debe reflejar que ahora le corresponde al jugador 2  
**And** este comportamiento debe repetirse alternando los turnos hasta que termine la partida.

### Escenario 6.2: Mostrar el resultado para ambos jugadores
**Given** que la partida en modo multijugador local ha terminado  
**When** el juego detecta un ganador  
**Then** debe mostrar quién ganó (jugador 1 o jugador 2, o "X" / "O")  
**And** ambos jugadores deben poder ver claramente el resultado en pantalla.

---

## 7. Modo de Juego contra la Computadora (IA)

### Escenario 7.1: Seleccionar modo contra la computadora
**Given** que el usuario está en la pantalla inicial del juego  
**When** selecciona el modo "Jugar contra la computadora"  
**Then** el juego debe configurarse para que un jugador sea humano y el otro sea controlado por la IA  
**And** debe indicarse claramente quién es el jugador humano y quién es la computadora.

### Escenario 7.2: Turno de la computadora
**Given** que la partida está en modo contra la computadora  
**And** el jugador humano ha realizado una jugada válida  
**When** termina el turno del jugador humano  
**Then** la computadora debe realizar automáticamente un movimiento válido en el tablero  
**And** después de la jugada de la computadora, el turno debe volver al jugador humano.

### Escenario 7.3: Dificultad de la IA (cuando aplique)
**Given** que el juego ofrece diferentes niveles de dificultad para la computadora (por ejemplo: fácil, medio, difícil)  
**When** el usuario selecciona un nivel de dificultad antes de iniciar la partida  
**Then** el comportamiento de la IA debe ajustarse a la dificultad elegida  
**And** la experiencia de juego debe sentirse más sencilla o más desafiante según la selección.

---
