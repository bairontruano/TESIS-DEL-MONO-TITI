# TESIS-DEL-MONO-TITI

SI HAY ERROES EN GITHUB, IR DIRECTAMENTE AL .ZIP del ONEDRIVE
https://javerianacaliedu-my.sharepoint.com/:f:/g/personal/amongrimorio_javerianacali_edu_co/IgAispVjUMtpQZfMrUjISW2eAfF-X--aYLPa8thWSeTDguI?e=YaKT9a



README: Scripts Principales del Proyecto
Este proyecto utiliza tres scripts clave para manejar la interacción con botones, la lógica de juego por fases, la vibración en controladores XR y la navegación entre escenas.

1. ButtonBuzz.cs: Feedback háptico en botones XR (OpenXR)

Descripción:
Este script añade vibración al controlador VR cuando se presiona un botón de la interfaz (UI). Está pensado para dispositivos XR compatibles con OpenXR, como Meta Quest.

Funcionalidad principal:
Detecta el evento onClick de un botón UI

Envía un impulso háptico al controlador izquierdo o derecho

Proporciona retroalimentación táctil inmediata al usuario

Requisitos:
Componente Button en el mismo GameObject

Controladores XR activos y compatibles con haptics

Parámetros configurables:
Hand: Mano que vibrará (Left o Right)

Amplitude: Intensidad de la vibración (0 a 1)

Duration: Duración de la vibración en segundos

Uso:
Añadir el script a un botón UI

Seleccionar la mano en el Inspector

Ajustar intensidad y duración según la experiencia deseada

2. ButtonSequenceController.cs: Controlador principal del juego por fases

Descripción:
Este es el script central del proyecto. Controla una secuencia de botones organizada en tres fases, con soporte para conteo de clics, reproducción de audios, timelines (PlayableDirector) e imágenes numéricas en pantalla.

Fases del juego:
Fase 1:
Botones principales que se activan en orden

Cada botón puede requerir varios clics

Soporte para modo conteo (visual y auditivo)

Reproducción de timelines al completar cada botón

Fase 2:
Aparecen botones adicionales

Existe un botón correcto configurable

Cada botón reproduce su propio timeline

Puede avanzar automáticamente a la fase 3 al presionar el botón correcto o esperar a completar todos

Fase 3:
Se activa un botón final

Se muestra un objeto exclusivo de esta fase

Al presionar el botón final se cambia de escena

Funcionalidades destacadas:
Activación y desactivación dinámica de botones

Conteo visual mediante imágenes

Audio diferenciado con y sin conteo

Manejo de PlayableDirector (Timeline)

Bloqueo de interacción durante animaciones

Control de flujo robusto para evitar dobles ejecuciones

Componentes requeridos:
Botones UI

AudioSources y AudioClips

PlayableDirector (opcional)

Toggle para modo conteo

Canvas con imágenes de números

Uso:
Asignar los botones de cada fase en el orden correcto

Configurar los clics requeridos por botón

Asignar audios y timelines según el modo de conteo

Definir el botón correcto de la fase 2

Configurar la escena final

3. MenuController.cs: Controlador del menú principal y cambio de escenas

Descripción:
Este script gestiona el menú principal del proyecto y la carga de escenas desde botones UI.

Funcionalidad principal:
Cargar una escena seleccionada desde el Inspector

Mostrar u ocultar el panel del menú

Salir de la aplicación (en builds)

Características:
En el Editor permite seleccionar la escena mediante SceneAsset

En runtime usa el nombre de la escena automáticamente

Compatible con botones UI estándar

Uso:
Añadir el script a un GameObject del menú

Asignar la escena desde el Inspector (Editor)

Vincular los métodos Jugar, Salir, MostrarMenu u OcultarMenu a botones UI

Notas generales:
Todos los scripts están diseñados para trabajar con UI de Unity

El flujo del juego está controlado principalmente por ButtonSequenceController_ClickPatterns_WithImages

ButtonBuzz puede combinarse con cualquier botón del proyecto para mejorar la sensación de interacción

El proyecto es compatible con XR y experiencias educativas o interactivas guiadas

