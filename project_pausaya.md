---
name: project-pausaya
description: "App Android PausaYa en desarrollo activo — recordatorio Regla 20-20-20, repo GitHub, keystore generado, CI/CD funcionando"
metadata: 
  node_type: memory
  type: project
  originSessionId: 90ccfbb8-db8f-4d61-807b-484845f75bdc
---

App Android minimalista de descanso visual llamada **PausaYa**. Se vende a $1 USD en Google Play.

**Repositorio:** https://github.com/kaelen-phoenix/claude  
**Cuenta GitHub:** kaelen-phoenix  
**Ruta local:** `/home/dev/claude`  
**Paquete:** `com.pausaya.eyerest`  
**Lenguaje:** Kotlin, minSdk 26, targetSdk 34

## Qué hace la app
Foreground service que notifica cada 20 minutos para aplicar la Regla 20-20-20 (mirar 6 metros por 20 seg). Timer preciso basado en tiempo real del sistema. Diseño oscuro minimalista.

## Archivos clave
- `app/src/main/java/com/pausaya/eyerest/EyeRestService.kt` — timer + notificaciones
- `app/src/main/java/com/pausaya/eyerest/MainActivity.kt` — UI + BroadcastReceiver
- `app/src/main/res/layout/activity_main.xml` — layout oscuro con timer 80sp
- `.github/workflows/build.yml` — CI/CD: compila y firma AAB en GitHub Actions

## Estado del CI/CD (al 2026-06-03)
- GitHub Actions workflow funcionando — build exitosa (run #26893231075)
- AAB firmado disponible como artefacto: `PausaYa-release-2`
- Keystore generado con keytool (Java 21 via apt)

## Credenciales y secretos
- **Keystore backup:** `/root/pausaya.jks.backup` (en el dispositivo local)
- **Alias:** `pausaya` | **Password:** `PausaYa2024!`
- **Secretos en GitHub:** `KEYSTORE_BASE64`, `STORE_PASSWORD`, `KEY_ALIAS`, `KEY_PASSWORD` (ya cargados)
- El keystore está en `.gitignore`, nunca se commitea

## Próximos pasos pendientes
1. Crear cuenta Google Play Developer ($25 USD) en https://play.google.com/console
2. Descargar AAB de GitHub Actions artifacts (run #26893231075)
3. Completar ficha de la tienda (descripción, capturas, ícono 512x512, feature graphic 1024x500)
4. Subir AAB a producción y publicar
5. Configurar precio $1 USD

**Why:** Experimento de app comercial simple, desarrollado 100% desde Android (Termux + navegador).  
**How to apply:** Cuando el usuario retome el desarrollo, verificar estado de la cuenta Play Console y si el AAB sigue disponible en Actions antes de sugerir próximos pasos.
