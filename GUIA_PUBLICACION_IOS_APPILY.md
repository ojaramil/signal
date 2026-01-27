# Guía de Publicación en iOS (App Store) con Appily App Builder

Esta guía te llevará paso a paso para publicar tu aplicación **Signal Radio** en la App Store de Apple, utilizando Appily App Builder y la estrategia de "Web View" que hemos preparado.

---

## 1. Requisitos Previos (Lo que necesitas sí o sí)

1.  **Cuenta de Desarrollador de Apple (Apple Developer Account):**
    *   **Costo:** $99 USD / año.
    *   **Dónde:** [developer.apple.com](https://developer.apple.com).
    *   **Importante:** Debes inscribirte como "Organización" (si tienes empresa) o "Individuo". Apple tarda unos días en verificar tu identidad. **No puedes publicar sin esto.**

2.  **Acceso a App Store Connect:**
    *   Es el portal donde gestionas la ficha de la App (textos, fotos, precio). Se activa automáticamente con tu cuenta de desarrollador.

3.  **URL de tu Web Móvil:**
    *   Asegúrate de que `https://signalradio.club/app-mobile.html` (o donde hayas alojado el archivo final) funciona perfectamente en el navegador de tu iPhone.

---

## 2. Configuración en Appily App Builder

1.  **Diseño de la App:**
    *   En el editor de Appily, selecciona una plantilla "En blanco" o "Blank".
    *   Añade **un solo módulo** llamado "Página Web", "HTML" o "External Link".
    *   **URL:** Pega la dirección de tu archivo optimizado: `https://signalradio.club/app-mobile.html`.
    *   **Navegación:** Desactiva la barra de navegación nativa de Appily y el menú lateral. Queremos que la App se vea "Full Screen" porque nuestro archivo HTML ya tiene su propia navegación inferior.

2.  **Datos de la App (Meta Data):**
    *   **Nombre:** Signal Radio.
    *   **Icono:** Sube tu logo (1024x1024 px, sin transparencias).
    *   **Pantalla de Carga (Splash Screen):** Sube una imagen vertical con tu logo y el fondo oscuro `#050510`.

3.  **Generar el "Build" (Compilación):**
    *   Ve a la sección "Publish" o "Publicación" en Appily.
    *   Selecciona "iOS".
    *   Te pedirá tus credenciales de Apple o subir certificados.
        *   *Opción Fácil:* Si Appily ofrece "Auto-upload" o "White Glove Service", úsalo. Ellos se encargan de los certificados.
        *   *Opción Manual:* Appily generará un archivo **.IPA** que tendrás que descargar.

---

## 3. Crear la Ficha en App Store Connect

1.  Entra a [appstoreconnect.apple.com](https://appstoreconnect.apple.com).
2.  Ve a "Mis Apps" -> Botón "+" -> "Nueva App".
3.  **Plataforma:** iOS.
4.  **Nombre:** Signal Radio.
5.  **Idioma:** Español (y Inglés como secundario si quieres).
6.  **Bundle ID:** Selecciona el ID que Appily creó para ti (ej. `com.signalradio.app`).
7.  **SKU:** Un código interno (ej. `signal-radio-v1`).

---

## 4. Subir el Archivo y Revisión

### Caso A: Si Appily sube el archivo por ti
Solo espera a que aparezca en App Store Connect en la sección "TestFlight".

### Caso B: Si descargaste el archivo .IPA
1.  Descarga la app **"Transporter"** desde la Mac App Store (en tu Mac).
2.  Abre Transporter e inicia sesión con tu cuenta Apple ID.
3.  Arrastra el archivo `.ipa` dentro de Transporter y dale a "Entregar" (Deliver).
4.  Espera a que termine la carga.

---

## 5. Preparar para Revisión (La Ficha de la Tienda)

Mientras se procesa el archivo (tarda unos 20 min), rellena la info en App Store Connect:
*   **Capturas de pantalla:** Sube fotos de la app funcionando (puedes tomarlas desde tu iPhone abriendo la web móvil).
*   **Descripción:** Explica el valor de la radio y la comunidad neurodivergente.
    *   *Tip:* Menciona la funcionalidad de reproducción en segundo plano si Appily la soporta.
*   **Palabras clave:** Radio, Autismo, Neurodivergencia, Podcast, Inclusión.
*   **URL de Soporte:** Tu web principal.
*   **Clasificación de Edad:** 4+ (o 12+ si hay temas complejos).

---

## 6. Enviar a Revisión

1.  En la pestaña "App Store", baja hasta "Compilación" (Build).
2.  Haz clic en "Seleccionar compilación" y elige la versión que acabas de subir.
3.  **Preguntas de Exportación:** Responde "No" a la encriptación (a menos que uses HTTPS complejo, pero generalmente es No o "Sí, estándar").
4.  Haz clic en **"Enviar para revisión"** (Submit for Review).

### ⏳ Tiempo de Espera
Apple suele tardar entre **24 y 48 horas** en revisar tu App.
*   **Si la rechazan:** No te asustes. El motivo más común para Apps basadas en web es "Guideline 4.2 - Minimum Functionality".
    *   *Solución:* Responde explicando que no es solo una web, que tiene funciones de audio nativo, notificaciones push (si las activaste en Appily) y una experiencia diseñada específicamente para móvil ("App-like experience").

¡Mucha suerte!
