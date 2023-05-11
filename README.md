# Diagrama de clases

## Herencia

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

## Realización 

```mermaid
classDiagram
interface Entrenarmiento {
    +void calentar(time : String): String
    +void entrenar(): String
    +void estirar(): String
}
class Ciclismo implements Entrenamiento {
    + String ejercicios
    + int participantes
}
class Baloncesto implements Entrenamiento {
    + String equipo
    + double alturaAro
}
```

