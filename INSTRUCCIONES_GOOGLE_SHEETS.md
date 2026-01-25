# Cómo Conectar el Widget de Comentarios a Google Sheets

Sigue estos pasos para que los mensajes lleguen directamente a una hoja de cálculo de Google. ¡Es gratis y no requiere servidor!

## Paso 1: Crear la Hoja de Cálculo
1. Ve a [Google Sheets](https://sheets.new) y crea una nueva hoja.
2. Llámala como quieras, por ejemplo: `Mensajes Radio Signal`.
3. En la primera fila (encabezados), escribe lo siguiente en las columnas A, B, C y D:
   - **A1**: `Fecha`
   - **B1**: `Nombre`
   - **C1**: `Correo`
   - **D1**: `Mensaje`

## Paso 2: Crear el Script (El puente)
1. En la hoja de cálculo, ve al menú **Extensiones** > **Apps Script**.
2. Se abrirá una nueva pestaña. Borra todo el código que aparece ahí y pega este:

```javascript
function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var data = JSON.parse(e.postData.contents);
  
  sheet.appendRow([
    new Date(),
    data.nombre,
    data.correo,
    data.mensaje
  ]);
  
  return ContentService.createTextOutput(JSON.stringify({"result":"success"}))
    .setMimeType(ContentService.MimeType.JSON);
}
```

3. Haz clic en el icono de **Guardar** (el disquete) y ponle un nombre al proyecto (ej. `Backend Comentarios`).

## Paso 3: Publicar el Script
1. Haz clic en el botón azul **Implementar** (arriba a la derecha) > **Nueva implementación**.
2. En la ventana que sale:
   - Haz clic en el engranaje (Tipo) y selecciona **Aplicación web**.
   - **Descripción**: `Versión 1`.
   - **Ejecutar como**: `Yo` (tu correo).
   - **Quién tiene acceso**: Selecciona **Cualquier usuario** (Esto es vital para que funcione desde la web).
3. Haz clic en **Implementar**.
4. Te pedirá permisos. Autoriza todo (si sale "Google no ha verificado esta aplicación", dale a "Configuración avanzada" y luego a "Ir a Backend Comentarios (inseguro)").
5. Copia la **URL de la aplicación web** que te dará al final. (Empieza por `https://script.google.com/macros/s/...`).

## Paso 4: Conectar con la Página Web
1. Pega esa URL en el código de tu página web donde dice `TU_URL_DE_GOOGLE_SCRIPT_AQUI`.
