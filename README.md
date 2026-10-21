FFLVoteBot - 

========================

INICIAR
-------
1. Extraé la carpeta FFLVoteBot completa.
2. En Windows, hacé doble clic en INICIAR_FFLVoteBot.bat.
3. En el menú, completá las tres secciones:
   - Cargar partida: URL del tema, identificador único, fase/día y enlace del post que abre esa fase.
   - Cargar lista de jugadores: lista completa y lista de vivos.
   - Cargar valor de voto: valor normal y reglas especiales por jugador.
4. Cuando los datos estén completos, pulsá INICIAR BOT.
5. Se abrirá Chromium en Fanficslandia antes de iniciar la lectura. Iniciá
   sesión manualmente y, cuando termines, volvé a la consola negra y presioná
   ENTER. Recién entonces el bot continuará y cerrará esa ventana inicial.
   El perfil persistente de Chromium guarda la sesión para las revisiones.

LECTURA DESDE EL INICIO DE CADA FASE
------------------------------------
- En Cargar partida, pegá la URL directa al mensaje del GM que anuncia el inicio
  de la fase actual (el enlace debe incluir #post-ID; puede incluir /page-N).
- El bot ignora el mensaje del GM y todos los posts anteriores. Solo procesa
  publicaciones posteriores al post ancla.
- Al cambiar el enlace de inicio de fase, el cursor de lectura se reinicia a ese
  post y se limpian los votos/recuento anteriores para no arrastrar votos de la
  fase previa. El bot vuelve a leer desde el inicio indicado.
- Si el campo queda vacío, se conserva el modo de lectura anterior.
- Si el bot ya está en marcha y cambia la fase, detenelo, actualizá el enlace,
  guardá la configuración y volvé a iniciarlo.

VALORES DE VOTO
---------------
- Normal: cada voto suma el valor normal configurado; admite decimales.
- Doble: el jugador emite un voto que vale 2 × el valor normal.
- Negativo: el voto de ese jugador vale -1 punto.
- Medio: el voto de ese jugador vale 0.5 puntos.
- Valor personalizado: permite asignar un valor fijo, por ejemplo 3, 0.5 o -1.5.
- El valor personalizado reemplaza el valor normal para ese jugador.
- Cada jugador puede tener una sola regla especial activa.
- La mayoría sigue calculándose por cantidad de jugadores vivos, no por puntos.
- El recuento ordena a los candidatos por puntuación neta y muestra el valor
  aportado por cada votante.

ARCHIVOS
--------
- configuracion.json: URL, ID de partida y parámetros del bot.
- partida.json: fase, día y jugadores vivos/muertos.
- jugadores.json: lista completa de participantes.
- valores_voto.json: valor normal y reglas especiales.
- votos.json / estado.json / tiempos.json: datos internos del seguimiento.

NOTAS
-----
- Se conserva la lógica existente de Selenium, lectura de posts y publicación.
- Usá un ID de partida distinto para cada mafia para evitar mezclar estados.
- No abras dos instancias del bot sobre el mismo perfil de Chrome a la vez.
- Al iniciar cada ejecución se espera confirmación manual de inicio de sesión.
- Si Python o Selenium no están instalados, ejecutá el instalador del proyecto
  original o instalá las dependencias que ya utilizabas.
