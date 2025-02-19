# Ejercicio: Caso Hotel

## Alejandro Casas Caicedo

### **Clases involucradas**

1. **Hotel:** Representa el hotel que gestiona las habitaciones, huéspedes y reservas.
2. **Habitacion:** Representa una habitación del hotel.
3. **Huesped:** Representa un huésped que realiza reservaciones en el hotel.
4. **Reserva:** Representa una reserva realizada por un huésped para una habitación en un tiempo específico.

### **Atributos y métodos principales**

#### 1. **Clase Hotel**

**Atributos:**

- **nombre: string** -> Nombre del hotel.
- **habitaciones: Habitacion[]** -> Contenedor de las habitaciones disponibles en el hotel.
- **huespedes: Huesped[]** -> Contenedor de los huéspedes registrados en el hotel.
- **reservas: Reserva[]** -> Contenedor con las reservas realizadas en el hotel.

**Métodos:**

- **agregarHabitacion(Habitacion habitacion)** -> Agrega una habitación al hotel.
- **agregarHuesped(Huesped huesped)** -> Registra un huésped en el hotel.
- **crearReserva(Reserva reserva)** -> Crea una nueva reserva.
- **actualizarEstadoReserva(Reserva reserva, string estado)** -> Actualiza el estado de una reserva.

#### 2. **Clase Habitacion**

**Atributos:**

- **numero: int** -> Número único de la habitación.
- **tipo: string** -> Tipo de habitación.
- **tarifaPorNoche: double** -> Tarifa por noche de la habitación.
- **disponible: boolean** -> Indica si la habitación está disponible.

**Métodos:**

- **getNumero()** -> Devuelve el número de la habitación.
- **getTipo()** -> Devuelve el tipo de habitación.
- **getTarifaPorNoche()** -> Devuelve la tarifa por noche.
- **estaDisponible(Date fechaInicio, Date fechaFin)** -> Verifica si la habitación está disponible en un periodo específico.
- **calcularCostoTotal(int noches)** -> Calcula el costo total de la reserva según el número de noches.

#### 3. **Clase Huesped**

**Atributos:**

- **id: int** -> Identificador único del huésped.
- **nombre: string** -> Nombre del huésped.
- **fechaRegistro: date** -> Fecha en que el huésped se registró en el hotel.
- **reservas: Reserva[]** -> Lista de reservas realizadas por el huésped.

**Métodos:**

- **getId()** -> Devuelve el ID del huésped.
- **getNombre()** -> Devuelve el nombre del huésped.
- **getFechaRegistro()** -> Devuelve la fecha de registro del huésped.
- **realizarReserva(Reserva reserva)** -> Permite al huésped realizar una reserva.
- **obtenerReservas()** -> Devuelve la lista de reservas del huésped.

#### 4. **Clase Reserva**

**Atributos:**

- **id: int** -> Identificador único de la reserva.
- **habitacion: Habitacion** -> Habitación reservada.
- **huesped: Huesped** -> Huésped que realizó la reserva.
- **fechaInicio: Date** -> Fecha de inicio de la reserva.
- **fechaFin: Date** -> Fecha de fin de la reserva.
- **estado: string** -> Estado de la reserva (por ejemplo, "activa", "completada").

**Métodos:**

- **getId()** -> Devuelve el ID de la reserva.
- **getHabitacion()** -> Devuelve la habitación reservada.
- **getHuesped()** -> Devuelve el huésped que realizó la reserva.
- **getFechaInicio()** -> Devuelve la fecha de inicio de la reserva.
- **getFechaFin()** -> Devuelve la fecha de fin de la reserva.
- **getEstado()** -> Devuelve el estado de la reserva.
- **setEstado(string estado)** -> Actualiza el estado de la reserva.
- **calcularDuracion()** -> Calcula la duración de la reserva en días.
- **calcularCostoTotal()** -> Calcula el costo total de la reserva.

### **Relaciones entre las clases:**

1. **Hotel - Habitacion**:

   - Un hotel tiene muchas habitaciones.
   - Cardinalidad: uno a muchos (1..*).
2. **Hotel - Huesped**:

   - Un hotel tiene muchos huéspedes.
   - Cardinalidad: uno a muchos (1..*).
3. **Hotel - Reserva**:

   - Un hotel tiene muchas reservas.
   - Cardinalidad: uno a muchos (1..*).
4. **Reserva - Habitacion**:

   - Una reserva está asociada a una sola habitación.
   - Cardinalidad: uno a uno (1..1).
5. **Reserva - Huesped**:

   - Una reserva está asociada a un solo huésped.
   - Cardinalidad: uno a uno (1..1).
6. **Huesped - Reserva**:

   - Un huésped puede realizar muchas reservas.
   - Cardinalidad: uno a muchos (1..*).
