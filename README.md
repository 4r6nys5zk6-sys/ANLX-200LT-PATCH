# ANLX Custom Patch LT V0.4.4 · Community

Parcheador **no oficial** para **Valeton GP-200LT con firmware V1.8.0**. Es un único archivo HTML que se abre localmente en el navegador. El HTML **no contiene el firmware oficial** y **no se conecta a la pedalera**: recibe un BIN que tú seleccionas y genera un ZIP con un nuevo BIN y `manifest.json`.

> [!WARNING]
> Hay un reporte de congelamiento de la pedalera y desaparición del bloque VOL relacionado con el trabajo pendiente para separar NAM e integrarlo con Universal Blocks. Antes de instalar, respalda presets y conserva el firmware oficial para restauración. Reiniciar puede recuperar una unidad congelada, pero **no corrige el bug**.

## 1. Mods incluidos

Se instalan automáticamente, sin casillas:

| Mod | Estado | Detalle |
| --- | --- | --- |
| **Universal Blocks** | Incluido, experimental | Selección de familias de efectos/NONE en los bloques. Conserva la corrección Delay/Slapback incorporada desde el checkpoint Developer. **NAM no se añade como familia activa.** |
| **Fast patch change** | Incluido | Reduce la transición al cambiar presets, adaptado a partir del mod de TNT. |
| **DSP Usage Meter** | Incluido | Indicador de carga de procesamiento DSP. |
| **Cry Baby GCB95 (C-Wah)** | Incluido | Recreación digital sin medición de una unidad física de referencia. |
| **Arranque ANLX V0.4.4** | Incluido | Imagen retro a resolución 480 × 272, preparada como GIF estático. Se puede sustituir en la interfaz. |

** El bloque NAM independiente y su enlace con Universal Blocks siguen **pendientes de implementación y validación**.

Los mods de TNT **Strobe tuner and footswitch LED indicators, Carry-over tap tempo, Global output balance, Footswitch labels, Unlock all display languages y Portuguese (Brazil) display language** no se ofrecen como nuevas instalaciones desde ANLX. Deben seleccionarse en el proyecto original de TNT. Los ya presentes se conservan únicamente cuando su combinación es reconocida y compatible.

## 2. Instalación desde TNT y ANLX

### Requisitos

- Una **Valeton GP-200LT**, no una GP-200, GP-200JR ni otra variante.
- Firmware oficial **GP-200LT V1.8.0** correspondiente a tu pedalera.
- Editor/software oficial Valeton compatible con V1.8.0, cable USB confiable y alimentación estable.
- Copia de seguridad de presets y del firmware original.
- Archivos: `GP-200-patcher.html` de TNT y `ANLX-CUSTOM-PATCH-LT-v0.4.4-COMMUNITY.html` de este repositorio.

Enlaces: [firmware oficial GP-200LT V1.8.0](https://www.valeton.net/wpfd_file/gp-200lt-firmware-v1-8-0-zip%EF%BC%88compatible-software-v1-8-0%EF%BC%89/), [TNT GP-200 Patcher, releases](https://github.com/tntexplosivesltd/gp200-patcher/releases), [Valeton GP-200LT](https://www.valeton.net/product/gp-200lt/).

### Ruta A: instalar primero parches de TNT

1. Descarga el **HTML de TNT v1.0** de su página de lanzamientos. Ábrelo en un navegador; funciona sin conexión.
2. Carga en TNT el **BIN oficial GP-200LT V1.8.0**. Selecciona allí los mods TNT que desees. **No es obligatorio seleccionar ninguno** si prefieres usar directamente ANLX desde el firmware original.
3. Genera la salida TNT. **Extrae el archivo `.bin` del ZIP** que produce TNT. Conserva el `manifest.json`, que documenta los cambios y sus huellas SHA-256.
4. Abre el HTML de **ANLX Community V0.4.4**. Carga el **BIN producido por TNT**, no el ZIP. Si se reconoce la combinación, el parcheador mostrará los mods ya presentes y preparará la lista Community automáticamente.
5. Si ANLX rechaza el BIN, **no cambies el nombre, la firma, los offsets ni el checksum para forzarlo**. Comienza desde el BIN oficial o reporta el SHA-256 y el manifiesto sin compartir datos privados.
6. Pulsa **Generar y descargar ZIP**. Descomprímelo y conserva los archivos `.bin` y `manifest.json` que generó ANLX.
7. Abre el **editor oficial de Valeton**, conecta la GP-200LT por USB y utiliza la opción de **actualización de firmware** del editor para cargar el `.bin` extraído. **No cargues el ZIP en el actualizador.** Sigue las indicaciones del editor hasta finalizar y no desconectes el cable ni la alimentación durante el proceso.
8. Al volver a encender, comprueba el arranque, los bloques incluyendo VOL, tus presets y el comportamiento de cambios de preset y Delay/Slapback antes de utilizar el equipo en directo.

### Ruta B: instalación sin mods TNT adicionales

1. Abre el HTML ANLX.
2. Carga directamente el **BIN oficial GP-200LT V1.8.0**.
3. Genera el ZIP de ANLX, extrae el BIN e instálalo desde el editor oficial como se explicó arriba.


## 3. Problema conocido: congelamiento / bloque VOL

**Síntoma reportado:** en las pruebas de integración NAM + Universal Blocks de la rama Developer, NAM aún no está convertido correctamente en bloque independiente y se ha observado congelamiento.

**Si el pedal se congela:** si es seguro hacerlo y no está actualizando firmware, apaga y vuelve a encender de forma normal. No repitas el preset o secuencia que causó el fallo. Si reaparece, restaura el firmware oficial siguiendo el procedimiento de Valeton. Si no arranca o queda en modo de actualización, utiliza el procedimiento de recuperación de firmware documentado por Valeton/TNT o solicita soporte. **No interrumpas la alimentación durante una actualización.**

Para reportar: especifica modelo, versión de boot, versión de editor, BIN de entrada, nombres de mods, pasos para reproducir. Adjunta `manifest.json` y el SHA-256 del BIN, no necesariamente el BIN completo.

## 4. Registro de cambios

### V0.4.4 · Community, (15 de noviembre de 2026)

- **Universal Blocks standalone** activado automáticamente, sin registrar la familia NAM todavía.
- **NAM A2 Lite**. Integración NAM + UB identificada como pendiente.
- implementación de Cry Baby GCB95 sobrescribe C-wah.
- **Fast Patch Change**, medidor DSP y arranque ANLX incluidos automáticamente.
- Importación de BIN oficial V1.8.0, **TNT v1.0 reconocido** verificada. Las rutas no comprobadas se rechazan.
- Nueva imagen de arranque 


## 5. Seguridad, créditos y licencias

- **tntexplosivesltd (TNT):** parches originales y referencia de instalación. [Repositorio](https://github.com/tntexplosivesltd/gp200-patcher).
- **Goaltoday:** trabajo original del motor NAM. NAM no se habilita en la Community de esta versión.
- **Valeton:** fabricante y propietario del firmware oficial. Este repositorio **no distribuye** el firmware original.

**Licencia:** las contribuciones originales de ANLX de las que tenemos derecho a disponer se publican bajo GPL-3.0; consulta `LICENSE`. Los componentes de terceros retienen sus respectivos derechos y licencias. La presencia de un componente en el HTML no significa que ANLX sea titular de su código. **Es necesario revisar las licencias y los permisos de redistribución de las partes de TNT y otros componentes antes de una publicación definitiva.** El parcheador es un experimento independiente, sin afiliación, garantía ni soporte oficial de Valeton.
