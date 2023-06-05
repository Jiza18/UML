# Diagrama de clases

## Relaciones

### Herencia

 La herencia permite crear clases que reutilizan, extienden y modifican el comportamiento definido en otras clases.

```mermaid
classDiagram
Entrenamiento <|-- Ciclismo
Entrenamiento <|-- Baloncesto
class Entrenamiento {
    + String lugar
    + int time
}
class Ciclismo {
    + String ejercicios
    + int participantes
}
class Baloncesto {
    + String equipo
    + double alturaAro
}
```
 
### Realización

El concepto de realización refiere la implementación de un interfaz por parte de una clase. Una interfaz es un medio común para que los objetos no relacionados se comuniquen entre sí. Estas son definiciones de métodos y valores sobre los cuales los objetos están de acuerdo para cooperar. 

```mermaid
classDiagram
Ciclismo ..|> Entrenamiento
Baloncesto ..|> Entrenamiento
class Entrenamiento {
    +void calentar(time : String): String
    +void entrenar(): String
    +void estirar(): String
}
class Ciclismo {
    + String ejercicios
    + int participantes

    +void calentar(time : String): String
    +void entrenar(): String
    +void estirar(): String
}
class Baloncesto {
    + String equipo
    + double alturaAro

    +void calentar(time : String): String
    +void entrenar(): String
    +void estirar(): String
}
```

### Agreagacion

La agregación es un tipo de asociación que indica que una clase es parte de otra clase (composición débil).

```mermaid
classDiagram
class Ciclista{
    +String algo
}
class Entrenador{
    +String algo
}
Ciclista --o Entrenador
```

### Composicion

La composición significa utlizar objetos dentro de otros objetos.

```mermaid
classDiagram
Rutina --* Entrenamiento
class Entrenamiento{
    List<Rutina> rutinas
}
class Rutina{
        -int time
        -List<String> ejercicios
    }
```

# Diagrama de secuencia

```mermaid
sequenceDiagram
Profesor ->> Kahoot: New Game
Kahoot ->> Profesor: Code
Profesor ->> Alumno: Code
Alumno ->> Kahoot: Username
```

# Diagrama de actividad

```mermaid
flowchart TD
pd[Aceder a Login] --> dv{Opcion?}
dv -->|Acceder| idatos[Introducir datos] --> dv2{Datos correctos?}
dv2 -->|Si|susLogin[Acceder a la pagina]
dv2 -->|No|failLogin[Reintetar]
dv -->|Registrarse| pagReg[Acceder a Registro]
dv -->|Restablecer contraseña| pagCon[Acceder al proceso]
```

# Diagrama de estados

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Agachado
    Agachado --> Idle
    Saltando --> Idle
    Idle --> Caminando
    Idle --> Saltando
    Caminando --> Idle
    Caminando --> Corriendo
    Corriendo --> Idle
    Corriendo --> Saltando
    Caminando --> Agachado
```