# 📊 Prueba de telemetría

## Objetivo

Confirmar si el ejecutable `Kojiro.exe` realiza conexiones de red (posible telemetría) al estar en ejecución, usando herramientas locales sin depender de software externo.

## Pasos realizados

### 1. Verificación del proceso activo

Se ejecutó el siguiente comando en PowerShell para verificar si `Kojiro.exe` estaba corriendo:

```powershell
tasklist | findstr "Kojiro.exe"
```

### 2. Revisión de puertos utilizando netstat

Se identificaron los siguientes PID asociados durante el análisis:

- PID 2656
- PID 3252
- PID 12956
- PID 1432

### 3. Verificación de tráfico de red utilizando el monitor de recursos de Windows

Se abrió el Monitor de recursos (`resmon.exe`) y se navegó a la pestaña **Red**, filtrando por el proceso `Kojiro.exe`.

![Preview](/resources/TELEMETRY.es.png)

No se detectó actividad de red ni tráfico generado por el ejecutable.
