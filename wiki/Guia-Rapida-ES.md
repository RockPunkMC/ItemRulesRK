# Guía rápida en español

## Instalación

1. Apaga el servidor.
2. Coloca el JAR en `plugins/`.
3. Inicia el servidor.
4. Ejecuta `/itemrules doctor`.
5. Ejecuta `/itemrules gui`.

Todos los ejemplos vienen desactivados; una instalación nueva no cambia el gameplay.

## Crear una regla desde la GUI

1. Pulsa **Crear regla**.
2. Selecciona **Desde cero**.
3. Escribe un ID único en minúsculas, como `bloquear_perla_spawn`.
4. Captura el objeto desde la mano.
5. Elige los activadores, por ejemplo `RIGHT_CLICK` y `THROW`.
6. Selecciona mundos o regiones.
7. En acciones activa **Cancelar** y configura el mensaje.
8. Abre **Revisión final**, realiza una prueba y pulsa **Guardar y aplicar**.

El borrador se conserva aunque cierres el inventario o salgas del servidor. Nada se aplica hasta guardar y confirmar.

## Regla YAML sencilla

```yaml
rules:
  bloquear-perla:
    enabled: true
    priority: 100
    stop-processing: true
    hand: ANY
    item:
      material: ENDER_PEARL
    triggers:
      - RIGHT_CLICK
      - THROW
    conditions:
      worlds:
        mode: WHITELIST
        values:
          - world
    actions:
      cancel: true
      message:
        enabled: true
        value: "<#FF5555>No puedes usar perlas aquí."
    bypass-permission: ""
```

Después de editar YAML usa `/itemrules reload`. No uses `/reload` de Bukkit.

`bypass-permission: ""` significa que nadie evita la regla. Las reglas se aplican a jugadores normales sin exigirles ningún permiso.

