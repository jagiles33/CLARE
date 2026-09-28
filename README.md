# CLARE

Automatización de un flujo en una app Android de terceros, en teléfono físico,
usando [mobile-mcp](https://github.com/mobile-next/mobile-mcp) desde Claude Code.

## Requisitos en la laptop

- [Node.js](https://nodejs.org/) 20 o superior
- [Android Platform Tools](https://developer.android.com/tools/releases/platform-tools) (`adb` en el `PATH`)
- [Claude Code](https://code.claude.com/)

## Preparar el teléfono

1. Activar **Opciones de desarrollador** (tocar 7 veces "Número de compilación").
2. En Opciones de desarrollador:
   - Activar **Depuración USB**.
   - Xiaomi / Redmi / POCO: activar también **Depuración USB (ajustes de seguridad)**,
     sin esto los toques y el texto no llegan a la app.
   - **Pantalla activa** (no se apaga mientras carga).
   - Escalas de animación de ventana, transición y animador en **0.5x** o **desactivadas**.
3. Conectar por USB, aceptar el diálogo "¿Permitir depuración USB?" y verificar:

   ```bash
   adb devices
   # debe listar el teléfono como "device" (no "unauthorized")
   ```

4. Recomendado: activar **No molestar** y desactivar la actualización automática
   de la app en Play Store, para que la UI no cambie entre ejecuciones.

## Usar

```bash
git clone https://github.com/jagiles33/CLARE && cd CLARE
claude
```

La primera vez Claude Code pide aprobar el servidor `mobile-mcp` definido en
`.mcp.json`. Para comprobar que funciona, pídele:

> lista los dispositivos disponibles

La telemetría de mobile-mcp está desactivada en `.mcp.json`
(`MOBILEMCP_DISABLE_TELEMETRY=1`).
