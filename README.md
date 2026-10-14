# Edunexus
Correo único: estudiante@edunexus.edu o docente@edunexus.edu (según la pestaña que elijas).

Contraseña única: EduNexus2026*

Explicacion del taller del 20%
LINK DEL REPOSITORIO
https://github.com/cordojaraestufa-cpu/Proyecto-final2

LINK DE DESPLIEGUE DE VERCEL
proyecto-final2-ilo7-5kk0ss7kv-cordojaraestufa-cpu.vercel.app



<P>INFRAESTRUCTURA EXPLICADA DEL PROYECTO</P>
La carpeta dist/

 contiene la versión compilada y optimizada del proyecto lista para publicar en producción (en Vercel).   
 Ahí dentro hay:
 index.html: El documento principal donde se carga la aplicación web en el navegador.    
 
 empaquetados por Vite:   
 index-CS00JPCI.js: Todo el código de React y JavaScript unido y minificado en un solo archivo para que cargue rápido.   index-D40yv4Ke.css: Todos los estilos CSS comprimidos de la página. 

1. Arquitectura General y Stack Tecnológico
"La arquitectura del proyecto está basada en un modelo Frontend con React y Vite, respaldado por Supabase como backend en la nube (BaaS - Backend as a Service) para la gestión de base de datos y autenticación, y preparado para control de versiones con Git.

"La carpeta legacy/ almacena la primera versión estática del proyecto (desarrollada en HTML y CSS puros) antes de migrar la plataforma a componentes dinámicos en React. Contiene los maquetados base que sirvieron como prototipos interactivos para estructurar las secciones educativas."


1. clases/
El HTML: Define la estructura de la página donde se ven las lecciones: títulos de los temas, el contenedor donde iría el reproductor de video o la clase grabada y la lista con los temas del curso.

El CSS: Controla el maquetado tipo rejilla (grid) o columnas para que el video quede centrado a un lado y el listado de lecciones a la derecha, además de darle estilos a los botones de "Siguiente clase" o "Marcar como vista".

2. diplomas/
El HTML: Crea el marco digital del certificado. Incluye las etiquetas de texto con el nombre del estudiante, la fecha, el curso completado y la firma del profesor o la institución.

El CSS: Aplica los bordes decorativos, fuentes tipo manuscrita o elegantes, colores dorados/azules, y posiciona los elementos para que parezca un diploma real y quede listo para imprimir o guardar.

3. guias/
El HTML: Organiza el texto académico de estudio usando encabezados (<h1>, <h2>), párrafos, bloques de código, tablas comparativas y listas con los conceptos clave de cada materia.

El CSS: Da formato tipo documento de lectura o libro digital: ajusta el tamaño de letra, el interlineado para evitar la fatiga visual y los colores de resaltado para los títulos y conceptos importantes.

4. inicio de sesion/
El HTML: Contiene el formulario (<form>) con las cajas de texto (<input type="email">, <input type="password">) y los botones de enviarlo o de "Recuperar contraseña".

El CSS: Centra la tarjeta de login en la pantalla, define las sombras, los bordes redondeados del formulario y el efecto hover (cambio de color) en los botones al pasar el ratón.

5. materias-comple/
El HTML: Maqueta la retícula (grid) con las tarjetas de las asignaturas complementarias y de profundización.

El CSS: Aplica el diseño visual a cada tarjeta (sombras, bordes, imágenes de portada de cada materia) y los estados animados cuando el usuario pasa el cursor sobre una materia.

6. Opciones/
El HTML: Estructura el panel de configuración de la cuenta: campos para cambiar el nombre, avatar, foto de perfil, correo o preferencias del sistema.

El CSS: Organiza la interfaz por pestañas o secciones laterales limpias, dándole una apariencia de panel de administración (setting panel).

7. progreso/
El HTML: Define los contenedores para las métricas: etiquetas con porcentajes, etiquetas de las asignaturas y las barras de avance (<progress> o <div>).

El CSS: Aplica los estilos y colores a las barras de carga (por ejemplo, verde para tareas completadas, azul para en proceso) y maqueta los gráficos e indicadores visuales.

8. talleres/
El HTML: Construye la estructura de las guías prácticas e interactivas: las preguntas del taller, los campos para redactar las respuestas o cargar archivos, y las fechas límite de entrega.

El CSS: Destaca los bloques de actividades con colores de alerta/notificación, formatea las preguntas en tarjetas ordenadas y resalta el botón de enviar tarea.

src/
Es el corazón del código fuente en producción. Contiene toda la arquitectura de software basada en React + JavaScript + JSX. Aquí se procesa la interfaz de usuario, la navegación, la gestión de estados globales y las peticiones al servidor.

Desglose de Subcarpetas en src/

1components/:
¿Qué hace?: Guarda los componentes reutilizables del proyecto (como botones, barras de navegación/Navbar, tarjetas de materias, modales o pies de página/Footer).  
 Propósito: Evita duplicar código. En lugar de reescribir un menú en cada página, se crea una vez aquí y se importa donde se necesite. 

 2context/:
 ¿Qué hace?: Maneja la Context API de React para el estado global.   
 Propósito: Permite compartir información importante entre múltiples componentes sin pasar props de mano en mano. Por ejemplo: guardar los datos del usuario autenticado, el tema (modo oscuro/claro) o la sesión activa de Supabase.

 3data/:
 ¿Qué hace?: Almacena información estática o datos locales en formato JSON o JS.   
 Propósito: Guarda arreglos u objetos con información base (por ejemplo, el catálogo estático de materias, guías precargadas, preguntas frecuentes o listas de opciones).

 lib/:
 ¿Qué hace?: Contiene configuraciones de librerías externas y utilidades.   
 Propósito: Aquí se configura principalmente el cliente de Supabase (fichero supabaseClient.js), importando la URL del proyecto y la API Key pública para conectarse con la base de datos.

 pages/:
 ¿Qué hace?: Contiene los componentes principales que representan las pantallas o vistas completas de EduNexus (Home, Clases, Talleres, Guías, Perfil, Login etc...).   
 Propósito: Cada archivo dentro de esta carpeta ensambla varios componentes menores de components/ para formar la página final que ve el usuario. 

 services/:
 ¿Qué hace?: Maneja la capa de llamadas a la API / Backend.   
 Propósito: Separa la interfaz de la lógica de datos. Contiene las funciones asíncronas (async/await) que consultan, insertan, actualizan o eliminan información en la base de datos de Supabase.

 Archivos Raíz en src/

 App.jsx:
Es el componente principal o contenedor raíz de la aplicación. Define el enrutamiento (con React Router) y la estructura general de la maquetación (por ejemplo, mantener fijo el menú mientras cambian las páginas).

main.jsx:
Es el punto de entrada de JavaScript/React. Se encarga de tomar el componente <App/> y montarlo directamente en el elemento id="root" de el archivo index.html.

index.css:
Es la hoja de estilos global de la aplicación. Contiene las reglas CSS generales, variables de colores, fuentes, reseteo de márgenes o la integración de frameworks de estilos como Tailwind CSS.   

Es la carpeta que representa el Backend y la Base de Datos de la aplicación EduNexus. En lugar de montar un servidor propio en Node.js o Python desde cero, el proyecto utiliza Supabase, que es una plataforma BaaS (Backend as a Service) basada en la base de datos relacional PostgreSQL.

/Supabase

El archivo schema.sql dentro de la carpeta supabase/ guarda el script en SQL que crea toda la base de datos de la plataforma. 

  Contiene principalmente:

Las tablas: Estructura para guardar usuarios, materias, guías, talleres y el progreso de los alumnos.  
Las relaciones: Conexiones entre las tablas mediante claves (por ejemplo, qué taller pertenece a qué materia).  
La seguridad (RLS): Reglas para que cada estudiante solo pueda ver y modificar sus propios datos.

POR ULTIMO

Son los archivos de configuración raíz del proyecto. Esto es lo que hay en cada uno:

.env: Guarda las claves secretas y URLs privadas para conectar la app con Supabase. No se sube a GitHub por seguridad.

.env.example: Una plantilla pública que muestra qué nombres de variables requiere el proyecto, pero con valores vacíos.

.gitignore: Le indica a Git qué carpetas y archivos no deben subirse a GitHub (como .env o node_modules).

index.html: El archivo HTML base donde React se monta para mostrar toda la aplicación.

package.json: Guarda la lista de librerías instaladas (React, Supabase, Vite) y los comandos para ejecutar o compilar el proyecto.

package-lock.json: Asegura que todos los miembros del equipo descarguen exactamente las mismas versiones de las librerías.

README.md: La documentación en texto con la descripción del proyecto e instrucciones para ingresar y correrlo.

vite.config.js: Las reglas de configuración de Vite para saber cómo procesar React y generar la compilación final.