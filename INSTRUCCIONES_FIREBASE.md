# Cómo Configurar Firebase para el Chat de Signal Radio

Sigue estos pasos sencillos para activar el chat gratuito de tu radio. Solo te tomará 5 minutos.

## Paso 1: Crear el proyecto
1. Ve a [console.firebase.google.com](https://console.firebase.google.com/) e inicia sesión con tu cuenta de Google.
2. Haz clic en **"Crear un proyecto"** (o "Agregar proyecto").
3. Nombre del proyecto: `SignalRadioChat`.
4. Acepta los términos y haz clic en **Continuar**.
5. Desactiva "Google Analytics" (no es necesario para esto) y haz clic en **Crear proyecto**.
6. Espera a que termine y haz clic en **Continuar**.

## Paso 2: Crear la Base de Datos
1. En el menú de la izquierda, busca **"Build"** (o Compilación) y selecciona **"Realtime Database"**.
2. Haz clic en el botón **"Crear base de datos"**.
3. Ubicación: Deja la que sale por defecto (ej. Estados Unidos) y da clic en **Siguiente**.
4. **IMPORTANTE:** En reglas de seguridad, selecciona **"Comenzar en modo de prueba"** (Start in test mode).
   * *Esto permitirá que cualquiera pueda escribir en el chat por ahora.*
5. Haz clic en **Habilitar**.

## Paso 3: Obtener las claves (Lo que necesito)
1. En el menú de la izquierda, haz clic en el ícono de **engranaje** (Configuración) al lado de "General description del proyecto" y selecciona **"Configuración del proyecto"**.
2. Baja hasta el final de la página donde dice **"Tus apps"**.
3. Haz clic en el ícono de **Web** (`</>`).
4. Apodo de la app: `RadioWeb`.
5. Haz clic en **Registrar app**.
6. Verás un bloque de código que dice `const firebaseConfig = { ... }`.
7. **Copia todo ese bloque de código** y envíamelo por aquí.

Se verá algo así:
```javascript
const firebaseConfig = {
  apiKey: "AIzaSyD...",
  authDomain: "signalradiochat.firebaseapp.com",
  databaseURL: "https://signalradiochat-default-rtdb.firebaseio.com",
  projectId: "signalradiochat",
  storageBucket: "signalradiochat.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef"
};
```

¡Eso es todo! Con eso podré conectar el chat.
