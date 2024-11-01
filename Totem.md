
En el chat:
/scoreboard objectives add Totems minecraft.used:minecraft.totem_of_undying

En los bloques de comandos:

execute as @e if score @s Totems matches 1 run tellraw @a [{"text":"El jugador ","color":"red"},{"selector":"@s"},{"text":" ha usado un tótem","color":"red"}]

execute as @e if score @s Totems matches 1 run scoreboard players reset @s Totems
