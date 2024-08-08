# Constructores-con-mas-puntos-ganados

Este proyecto es una aplicación Java que utiliza JDBC para interactuar con una base de datos PostgreSQL. La aplicación muestra estadísticas de Fórmula 1, incluyendo los conductores con más puntos ganados.

## Configuración

1. Clona el repositorio.
2. Configura tu base de datos PostgreSQL y asegúrate de que está corriendo en `localhost` en el puerto `5432`.
3. Crea una base de datos llamada `formula1`.
4. Actualiza las credenciales de la base de datos en los archivos de repositorio si es necesario.

## Mostrar Conductores con Más Puntos

Para mostrar los conductores con más puntos ganados:

1. Asegúrate de tener la clase `DriverMaxPoints` en el paquete `demo_jdbc.models`.
2. Asegúrate de tener la clase `DriverMaxPointsRepository` en el paquete `demo_jdbc.repositories`.
3. Llama al método `getDriversWithMaxPoints` desde tu clase `Main` y muestra los resultados.

### Ejemplo de Uso

```java
package demo_jdbc;

import demo_jdbc.models.DriverMaxPoints;
import demo_jdbc.repositories.DriverMaxPointsRepository;

import java.util.List;

public class Main {
    public static void main(String[] args) {
        DriverMaxPointsRepository repository = new DriverMaxPointsRepository();
        List<DriverMaxPoints> drivers = repository.getDriversWithMaxPoints();

        System.out.println("Conductores con más puntos:");
        for (DriverMaxPoints driver : drivers) {
            System.out.println("ID: " + driver.getDriverId() + ", Nombre: " + driver.getDriverName() + ", Puntos: " + driver.getTotalPoints());
        }
    }
}
