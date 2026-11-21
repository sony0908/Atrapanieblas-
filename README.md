# Atrapanieblas · Chile Re-Descubre (Congreso Futuro 2027)

Videojuego de estrategia y gestión en pixel art isométrico inspirado en la innovación chilena de los **atrapanieblas** en la costa desértica del norte de Chile.

## Campaña (un solo recorrido)
El juego tiene un único modo: **Campaña**, que siempre parte con una malla y una caleta pequeña, recorre el **Nivel 1** y desemboca en el **Nivel 2**.
- **Intro del Nivel 1**: al cargar el juego se reproduce una cinemática de 6 escenas que explica el desierto, la camanchaca, las mallas y el agua para la caleta.
- **Intro del Nivel 2**: al completar la red se reproduce una segunda cinemática sobre la sal, la mantención, las ráfagas y la señal de enrollado.
- **Avance rápido**: cualquier tecla o toque pasa a la siguiente escena; `Esc` o el botón **Saltar intro** termina la cinemática completa. Si no se toca nada, las escenas avanzan solas.
- Al terminar cada intro, el juego continúa en el nivel correspondiente (Nivel 1 o Nivel 2).

## Nivel 1 — Instala la red completa
- **Exploración y construcción**: toca las plataformas `(+)` en las cimas de los cerros costeros para instalar mallas y aprovechar la camanchaca.
- **Recolección activa**: toca las alertas `(!)` cuando se llene un bidón para despachar transportistas por los senderos.
- **Cañerías por malla**: toca **cualquier parte de una malla instalada** (no solo el bidón) para abrir su panel ampliado y comprarle su propia cañería. Cada cañería se compra de a una (su costo depende de lo lejos que esté la malla), se tiende desde la malla hasta la caleta y el agua baja sola por gravedad. Al conectarse, esa malla deja de acumular bidón: desaparece la alerta `(!)` y ya no necesita transportista.
- **Consumo y sequía**: la población consume agua continuamente; si los estanques se vacían, los huertos se secan, baja la población y las casas comienzan a ser abandonadas hasta que vuelve el agua.
- **Crecimiento y mejoras**: aumenta el agua almacenada para hacer crecer la caleta y mejorar el almacenamiento (tambores, estanque comunitario, copa de agua y red hídrica).
- **Fin del Nivel 1**: cuando **todas** las plataformas tienen su malla se reproduce la **intro del Nivel 2** y, al terminar (o saltarla), comienza el Nivel 2.

## Nivel 2 — Viento y sal
La red ya está completa, pero el desierto la castiga. Aparecen dos frentes de gestión simultáneos:

### Ráfagas de viento
- Una alarma anuncia la ráfaga **17 segundos antes** de que llegue: el aviso indica el sector y cuántas mallas están en riesgo. La cámara encuadra el pueblo y el sector (y el aviso es clickeable para volver a él).
- Cada malla en riesgo muestra una burbuja `⚠`: tócala (o usa `R`) para que el pueblo envíe una **señal remota** que viaja por el sendero y **enrolla la malla a distancia**, sin que un técnico tenga que subir.
- La señal se dibuja saliendo de la torre de la caleta: un pulso luminoso recorre el sendero hasta la malla y, al llegar, la malla se enrolla. El panel muestra el progreso de la señal.
- Si la ráfaga llega con la malla desplegada, pierde integridad, salta agua del bidón y puede **romperse** (deja de capturar).
- Las mallas enrolladas resisten sin daño, pero dejan de producir: tras la ráfaga hay que enviar la señal de **despliegue**.
- Cada ráfaga protegida sin daños suma al contador de **ráfagas resistidas** del HUD.

### Salinidad y mantención
- La humedad y la sal del desierto se acumulan en el paño: cuanto más densa la camanchaca (noche), más rápido sube la **salinidad**.
- Sobre el 50 % de sal la malla pierde caudal; sobre el 90 % la sal empieza a **estropear** la integridad hasta romperla.
- Cuando la salinidad pasa el 60 % aparece una burbuja `🧂`: envía un técnico a hacer **mantención** (limpia la sal y recupera parte de la integridad).
- Las mallas dañadas o rotas se **reparan** con caja de la caleta (`$22`) y un técnico.

### Cuadrilla técnica
- El Nivel 2 comienza con 2 técnicos; se pueden contratar hasta 4 con la **caja**.
- Cada técnico viaja desde la caleta y trabaja una malla a la vez: **mantención por sal** y **reparación** de mallas rotas. El **enrollado y despliegue** ya no requiere que suban: se resuelve con la señal remota.
- Panel `👷` (dock derecho / inferior en móvil): estado de cada técnico, contratación, **enrollar todas las mallas en riesgo por señal** y **mantención de todas las pendientes**.
- Si no hay técnicos libres, la tarea queda **en cola** y se asigna cuando uno se desocupa.

## HUD
- **Caja**: apartado propio destacado en oro, con el dinero disponible y la renta pasiva de los huertos (`+X/s`). Pulsa al recibir entregas y al gastar.
- **Nivel**: progreso de mallas (Nivel 1) o tareas pendientes y ráfagas resistidas (Nivel 2).
- **Panel de malla ampliado**: al tocar cualquier parte de una malla se abre su interfaz con una **vista ampliada animada** de la malla (desplegada, enrollada, rota, con costra de sal y aviso de ráfaga), su etiqueta de estado, Integridad, Salinidad, rendimiento, caudal, cañería, y botones de **enrollar/desplegar por señal**, **mantención**, **reparar**, **enviar transportista** (si el bidón está lleno) y **comprar cañería**.
- Chips de agua, población, transportistas, mallas y técnicos.
- **Aviso de ráfaga**: banner naranja con cuenta regresiva y sector afectado.
- Zonas táctiles ampliadas: burbujas `(!)`, `⚠` y `🧂`, mallas completas y botones del dock (42–46 px) pensados para pantallas táctiles.

## Controles
- Arrastrar: mover cámara · Rueda / pinza: zoom.
- Tocar una **malla**: abre su panel ampliado de estado, cañería y técnicos.
- `Espacio`: ir a la siguiente alerta de agua · `R`: enviar señal de enrollado a las mallas en riesgo · `M`: mantención pendiente · `T`: ir a la primera tarea técnica · `C`: centrar caleta.
- Durante las intros: **cualquier tecla o toque avanza de escena** · `Esc` o **Saltar intro** termina la cinemática.

## Cinemáticas
Las dos intros están **integradas en `index.html`** y se reproducen sobre el juego:
- **Intro Nivel 1**: desierto, caleta sin agua potable, camanchaca, malla atrapando gotas, cañería por gravedad y caleta floreciendo.
- **Intro Nivel 2**: sal cristalizada, caída del caudal, mantención, ráfaga, señal de enrollado y despliegue/revisión.
- Cada escena lleva un **rótulo breve con titular y una línea explicativa**, ubicado arriba o abajo según la composición para no tapar la acción.
- El archivo `animaciones.html` queda como **versión de revisión independiente**: incluye reproductor con pausa, línea de tiempo, storyboard con miniaturas, velocidad y sonido ambiente generado.

## Ejecución local y despliegue
Proyecto estático HTML5 (`index.html`). Compatible con despliegue directo en **Vercel** sin paso de build.
