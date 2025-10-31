# Análisis de Comandos de Procesos en Linux

Este documento explica varios comandos utilizados para monitorear procesos en un sistema Linux, basándose en las capturas de pantalla proporcionadas.

## 1. Comando: htop

`htop` es un visor de procesos interactivo y avanzado. Ofrece una vista en tiempo real, mucho más visual y fácil de usar que el `top` tradicional. Muestra el uso de CPU por núcleo, el consumo de memoria y swap, la carga media y una lista de procesos que se puede ordenar y filtrar fácilmente.

![Salida de htop](htop_6.png)

---

## 2. Comando: ps au

El comando `ps au` muestra los procesos de **todos los usuarios** (`a`) en un formato **orientado al usuario** (`u`). Este formato incluye columnas útiles como `USER`, `PID`, `%CPU`, `%MEM`, estado (`STAT`) y el comando completo.

![Salida de ps au](ps_1.png)

---

## 3. Comando: ps aux

El comando `ps aux` es muy similar a `ps au`. La opción `x` (estilo BSD) se asegura de incluir también los procesos que **no están asociados a ninguna terminal** (como los demonios o servicios del sistema). Es una de las formas más comunes de obtener una instantánea completa de *todos* los procesos en ejecución.

![Salida de ps aux](psaux_2.png)

---

## 4. Comando: ps -u alumno

Este comando filtra la lista de procesos para mostrar únicamente aquellos que pertenecen al usuario especificado, en este caso, "alumno". Es útil para ver qué está ejecutando un usuario en particular.

![Salida de ps -u alumno](ps-u_3.png)

---

## 5. Comando: ps -eo ... | head ...

Este es un uso avanzado de `ps` para obtener información muy específica.
* `ps -eo user,pid,comm,%cpu`: Muestra todos los procesos (`e`) con un formato de salida personalizado (`-o`), seleccionando solo las columnas de usuario, PID, nombre del comando y %CPU.
* `--sort=-%cpu`: Ordena la salida por la columna %CPU en orden descendente (el `-` indica de mayor a menor).
* `| head -n 6`: Envía el resultado al comando `head`, que muestra solo las primeras 6 líneas (la cabecera más los 5 procesos que más CPU consumen).

![Salida de ps con formato y orden personalizado](comando_informacion_selectiva_7.png)

---

## 6. Comando: top (Modo Interactivo)

Esta es la vista estándar del comando `top` en su modo interactivo. Proporciona un resumen dinámico y en tiempo real del estado del sistema (carga, tareas, memoria) y una lista de los procesos que más recursos consumen, la cual se actualiza automáticamente.

![Salida de top interactivo](top_4.png)

---

## 7. Comando: top -b -n 3 > top.info (Modo Batch)

Esta imagen muestra el resultado de ejecutar `top` en "modo batch" o no interactivo (`-b`), lo que permite que su salida sea redirigida.
* `top -b -n 3 > top.info`: Ejecuta `top`, toma 3 "fotos" o iteraciones (`-n 3`) y guarda toda esa salida en un archivo llamado `top.info`.
* `cat top.info`: (Comando ejecutado para ver el archivo) Muestra el contenido del archivo `top.info` que se acaba de crear.

![Salida de top en modo batch guardado en un archivo](top_5.png)
