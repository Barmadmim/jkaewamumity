# Seguimiento del Uso de Tótems en Minecraft

Este documento describe cómo configurar un sistema para rastrear el uso de tótems de inmortalidad en Minecraft utilizando bloques de comandos y el sistema de puntuaciones.

## Reglas del Juego

Para evitar la retroalimentación de comandos en el chat, asegúrate de establecer la siguiente regla de juego:

```bash
/gamerule sendCommandFeedback false
```

Esta regla desactiva la retroalimentación que se muestra en el chat cuando se ejecutan comandos, lo que ayuda a mantener el chat limpio y libre de mensajes innecesarios.

Configuración del Marcador de Tótems
Para llevar la cuenta de cuántos tótems ha usado un jugador, sigue estos pasos:

Crear el Marcador de Tótems Usados

Ejecuta el siguiente comando para agregar un marcador que rastree el uso de los tótems:

```bash
/scoreboard objectives add Totems minecraft.used:minecraft.totem_of_undying
```

Este comando crea un nuevo objetivo llamado Totems que incrementa su puntuación cada vez que un jugador usa un tótem de inmortalidad.

Bloques de Comandos
A continuación, se describen los comandos que debes utilizar en tus bloques de comandos para mostrar un mensaje en el chat cuando un jugador use un tótem:

Mostrar Mensaje en el Chat

Coloca un bloque de comandos configurado como "Repetir" y "Incondicional" con el siguiente comando:

```bash
execute as @e if score @s Totems matches 1 run tellraw @a [{"text":"El jugador ","color":"red"},{"selector":"@s"},{"text":" ha usado un tótem","color":"red"}]
```

Este comando ejecutará un mensaje en el chat cada vez que un jugador use un tótem de inmortalidad.

Restablecer el Marcador de Tótems

Coloca otro bloque de comandos configurado como "Repetir" y "Incondicional" con el siguiente comando:

```
execute as @e if score @s Totems matches 1 run scoreboard players reset @s Totems
```
Este comando restablecerá la puntuación del marcador Totems a 0 después de que se haya mostrado el mensaje.
