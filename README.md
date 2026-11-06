# 🎾 Ping Pádel

Aplicación Android para **reservar pistas de pádel, encontrar jugadores y llevar el control de tus partidos y tu nivel**. Desarrollada como Trabajo de Fin de Grado del ciclo de **Desarrollo de Aplicaciones Multiplataforma (DAM)** en el IES Poeta Paco Mollá (Petrer, Alicante).

## ✨ Funcionalidades

- **Registro e inicio de sesión** de usuarios, con recuperación de datos desde la pantalla de login.
- **Reserva de pistas:** elige un club, una fecha y una pista/franja horaria (08:00 a 14:00, en tramos de 1 h 30 min). La app marca los huecos ya ocupados y evita reservas duplicadas.
- **Clubes de pádel:** listado con logo e imagen de cada club (Petrer, Elda y Alicante), con diseño adaptado a vertical y horizontal mediante *fragments*.
- **Mis reservas:** consulta de tus próximas reservas en la pantalla principal y cancelación de las que ya no quieras.
- **Historial de partidos:** registro de partidos con pareja, rivales y resultado por sets (hasta 3), con validación de marcadores.
- **Encuentra jugadores:** buscador de otros usuarios por nombre o usuario, con filtro por nivel.
- **Calcula tu nivel:** cuestionario (frecuencia de juego, entrenamientos, torneos, posición y estilo) que asigna un nivel del 1 al 5 y lo guarda en tu perfil.
- **Buzón de mensajes:** envío y recepción de mensajes entre jugadores.
- **Perfil:** edición de nombre y ciudad, foto desde la galería y baja de la cuenta.
- **Ajustes:** notificaciones, modo oscuro y tamaño de fuente.
- **Menú lateral** (*navigation drawer*) para moverse entre todas las secciones.

## 🛠️ Tecnologías

| Área | Tecnología |
|------|------------|
| Lenguaje | Java 8 |
| Plataforma | Android (minSdk 24, compileSdk 35) |
| IDE y build | Android Studio, Gradle |
| Base de datos | SQLite (a través de `SQLiteOpenHelper`), almacenada en el propio dispositivo |
| Interfaz | XML, Material Components, ConstraintLayout, DrawerLayout, RecyclerView, Fragments |

## 🧱 Estructura del proyecto

```
app/src/main/java/dam/macr/proyecto_macr/
├── activities/   Pantallas: Login, SignUp, Main, Clubes, Reserva, Partidos,
│                 Resultados, Usuarios, Nivel, Buzón, Mensaje, Perfil, Config
├── adapters/     Adaptadores de las listas (clubes, reservas, partidos, usuarios, mensajes)
├── bd/           DBHelper: creación y consultas de la base de datos SQLite
├── fragments/    Lista de clubes e imagen del club
└── pojos/        Modelos: Club, Reserva, Partido, Usuario, Mensaje
```

### Modelo de datos

Base de datos SQLite `bd_pingpadel.db` con cinco tablas: `usuarios`, `clubes`, `reservas`, `partidos` y `mensajes`. Las reservas y los partidos se relacionan con los usuarios (y con los clubes en el caso de las reservas) mediante claves foráneas.

## 🚀 Cómo ejecutarlo

### Requisitos

- [Android Studio](https://developer.android.com/studio) (versión reciente)
- Un emulador o un móvil Android con Android 7.0 (API 24) o superior

### Pasos

1. Clona el repositorio:
   ```bash
   git clone https://github.com/castilloruiz29/ping-padel.git
   ```
2. Abre la carpeta en Android Studio (**File → Open**) y espera a que termine la sincronización de Gradle.
3. Selecciona un emulador o conecta tu móvil con la depuración USB activada.
4. Pulsa **Run ▶**.

No hace falta configurar ningún servidor: la base de datos se crea sola en el primer arranque, con datos de ejemplo (clubes y usuarios de prueba).

## 🔭 Posibles mejoras

- Guardar las contraseñas con *hash* en lugar de texto plano.
- Sustituir SQLite local por un backend (por ejemplo una API REST), para que las reservas y los mensajes se compartan entre dispositivos.
- Hacer que los ajustes (modo oscuro, notificaciones) se guarden de forma persistente.
- Migrar a Kotlin y a una arquitectura MVVM con Room.

## 👤 Autor

**Miguel Ángel Castillo Ruiz**
[LinkedIn](https://www.linkedin.com/in/miguel-ángel-castillo-ruiz-08581936a)
