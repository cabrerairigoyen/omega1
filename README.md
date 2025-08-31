# Omega with Pi Stream App

Esta es una versión personalizada de Omega que incluye la aplicación Pi Stream para mostrar datos desde Raspberry Pi.

## Características

- **Pi Stream App**: Aplicación personalizada para recibir y mostrar datos de Raspberry Pi
- **Construcción automática**: GitHub Actions compila automáticamente los binarios
- **Basado en Omega**: Utiliza la base de Omega 2.0.6 con Epsilon 15.5.0

## Instalación

1. Ve a la sección [Releases](../../releases) 
2. Descarga el archivo `omega.dfu` más reciente
3. Conecta tu calculadora Numworks en modo DFU
4. Usa NumWorks Workshop o dfu-util para flashear:

```bash
dfu-util -i 0 -a 0 -s 0x08000000:leave -D omega.dfu
```

## Desarrollo

La app Pi Stream se encuentra en `apps/pi_stream_app/` y incluye:

- `pi_stream_app.h/cpp`: Estructura principal de la aplicación
- `pi_stream_controller.h/cpp`: Controlador que maneja la interfaz
- Archivos de localización (*.i18n) para múltiples idiomas

## Build automático

Este repositorio está configurado para compilar automáticamente cuando haces push. Los binarios se generan como artifacts en GitHub Actions.

## Licencia

Basado en [Omega-Numworks/Omega](https://github.com/Omega-Numworks/Omega)