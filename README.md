# Torneo-esports-uml

## Autor
Noelia Prieto del Puerto
noeli22

## Descripción del Proyecto

Este proyecto implementa un sistema de gestión de torneos de eSports utilizando UML para el modelo. En este caso me he centrado solo en la gestion de jugadores y equipos. 
He diseñado una aplicación para gestión de torneos, usando un enfoque orientado a objetos con una interfaz CRUD (ICrudGameMaster) y una implementación concreta (GameMaster), con clases de entidad: Jugador, Equipo, Torneo y Participacion.

## Diagramas UML

### 🔷 Clases Principales

#### **Jugador**
- **Atributos:**
  - `nombreJugador: String`
  - `edad: int`
  - `idJugador: int`
  - `email: String`
  - `nickname: String`
- **Descripción:** Representa a un jugador individual. Cada jugador puede pertenecer a un único equipo.

#### **Equipo**
- **Atributos:**
  - `nombreEquipo: String`
  - `idEquipo: int`
  - `numParticipantes: int`
- **Descripción:** Cada equipo está formado por uno o más jugadores. Además, se registra su participación en diferentes torneos.

#### **Torneo**
- **Atributos:**
  - `idTorneo: int`
  - `nombreTorneo: String`
  - `fechaInicio: Date`
  - `fechaFin: Date`
  - `tipoJuego: String`
- **Descripción:** Un torneo puede tener múltiples equipos participantes.

#### **Participacion**
- **Atributos:**
  - `idEquipo: int`
  - `idTorneo: int`
- **Descripción:** Clase intermedia que modela la relación muchos-a-muchos entre `Equipo` y `Torneo`.

  
### 🔶 Lógica de Control

#### **ICrudGameMaster**
Interfaz que define las operaciones de gestión de entidades:

- `crearJugador()`, `crearEquipo()`, `crearTorneo()`
- `buscarJugador()`,  `buscarEquipo()`,  `buscarTorneo()`
- `modificarJugador()`, `modificarEquipo()`,`modificarTorneo()`
- `eliminarJugador()`, `eliminarEquipo()`, `eliminarTorneo()`
- `consultarJugadores()`, `consultarTorneos()`, `consultarEquipos()`

#### **GameMaster**
- Implementa `ICrudGameMaster`.
- **Contiene:**
  - `List<Jugador> jugadores`
  - `List<Equipo> equipos`
  - `List<Torneo> torneos`
- **Métodos:**
  - `registrarJugador()`
  - `registrarEquipo()`
- **Descripción:** Se encarga de administrar todos los elementos del sistema, centralizando la lógica de control.

### 🔗 Relaciones y Cardinalidad

- **Jugador** `* ─ 1` **Equipo**: un jugador pertenece a un equipo, un equipo puede tener múltiples jugadores.
- **Equipo** `* ─ *` **Torneo** (mediante `Participacion`): múltiples equipos pueden participar en múltiples torneos.
- **GameMaster** `1 ─ *` **Jugadores / Equipos / Torneos**: relación de composición. Si se elimina el `GameMaster`, también se eliminan las listas asociadas


### Diagrama de Casos de Uso
Este diagrama muestra las principales interacciones entre los actores y el sistema.
! [Diagrama de casos de uso](diagrams/casos-uso.png)

### Diagrama de Clases
Representa la estructura del sistema, incluyendo las clases principales, sus atributos, métodos y relaciones.
! [Diagrama de clases](diagrams/clases.png)

## Estructura del Proyecto

```
torneo-esports-uml/
├── src/
│   └── es/empresa/torneo/
│       ├── modelo/
│       ├── control/
│       ├── vista/
│       └── Main.java
├── diagrams/
│   ├── casos-uso.png
│   └── clases.png
├── README.md
└── .gitignore
```



## Instalación y Ejecución 
1. Clonar el repositorio:
`git clone https://github.com/noeli22/torneo-esports-uml.git`

## Conclusiones Sobre el aprendizaje obtenido.
Este proyecto me ha permitido afianzar el conocimiento en modelado UML. Además, ha reforzado habilidades en documentación y organización de proyectos.
