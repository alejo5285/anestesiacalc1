# AnestesiaCalc Pro — proyecto Android (Capacitor)

Este proyecto compila automáticamente un archivo .apk instalable
usando GitHub Actions (sin necesidad de instalar Android Studio).

## Cómo generar el .apk

1. Crea un repositorio nuevo y VACÍO en https://github.com/new
   (puede ser público o privado).
2. En la página del repo recién creado, haz clic en
   "uploading an existing file" (o arrastra la carpeta completa
   descomprimida a la ventana del navegador).
3. Sube TODO el contenido de esta carpeta (manteniendo la
   estructura de subcarpetas: www/, android/, .github/, etc.)
   y confirma el commit ("Commit changes").
4. Ve a la pestaña "Actions" de tu repositorio. Debería aparecer
   un workflow llamado "Build Android APK" ejecutándose
   automáticamente (tarda 3-6 minutos).
5. Cuando termine (ícono verde ✓), entra a esa ejecución y baja
   hasta "Artifacts". Descarga "AnestesiaCalc-Pro-debug-apk.zip".
6. Descomprime ese zip: adentro está app-debug.apk. Pásalo a tu
   celular Android (por USB, Drive, WhatsApp a ti mismo, etc.) y
   ábrelo para instalarlo (activa "instalar apps de origen
   desconocido" si el sistema lo pide la primera vez).

## Si quieres compilarlo en tu propia computadora en vez de GitHub

Necesitas tener instalado Android Studio (que ya incluye el SDK
de Android) y Node.js. Luego:

    npm install
    npx cap sync android
    cd android
    ./gradlew assembleDebug

El .apk queda en android/app/build/outputs/apk/debug/app-debug.apk

## Actualizar la app cuando cambies el HTML

Reemplaza el archivo www/index.html por tu nueva versión, sube
el cambio a GitHub (commit), y Actions volverá a compilar el
.apk automáticamente.
