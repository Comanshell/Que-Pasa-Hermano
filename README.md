# Que Pasa Hermano

App de Android para llevar el colegio: notas por periodo, tareas, exámenes, horario y recordatorios. Los datos se quedan en el celular y no necesita internet para funcionar.

El diseño está basado en Apple Music. Las materias se ven como álbumes, y abajo hay un panel fijo, parecido al reproductor, con lo próximo que tienes.

<p align="center">
  <img src="docs/capturas/inicio.png" width="200" alt="Inicio">
  <img src="docs/capturas/materia.png" width="200" alt="Página de una materia">
  <img src="docs/capturas/periodos.png" width="200" alt="Notas por periodo">
</p>
<p align="center">
  <img src="docs/capturas/tareas.png" width="200" alt="Tareas">
  <img src="docs/capturas/horario.png" width="200" alt="Horario">
  <img src="docs/capturas/panel.png" width="200" alt="Panel expandido con temporizador">
</p>
<p align="center"><sub>Capturas con los datos de ejemplo que trae la app.</sub></p>

## Qué tiene

### Notas

- Cada materia tiene 4 periodos (o 3, si tu colegio trabaja así), y cada periodo lleva sus propias notas.
- Las notas pueden ir con porcentaje (quiz 20%, taller 30%, evaluación 50%) o valer todas lo mismo. Eso se escoge en cada materia.
- La nota del curso es el promedio de los periodos.
- Te dice cuánto necesitas en lo que queda del año para pasar la materia y cuánto te falta en el periodo en el que vas.
- También muestra qué promedio te haría falta para terminar con 3.5, 4.0, 4.5 o 5.0.
- La escala se puede cambiar: 0 a 5, 1 a 5, 0 a 10, 0 a 100 o una personalizada.

### Pasar el año

Si pierdes 3 materias, pierdes el año. La app lleva la cuenta de las materias perdidas y de las que están en riesgo, y avisa en Inicio cuando entre las dos llegan a 3. Si en tu colegio el número es otro, se cambia en Perfil.

### Tareas y exámenes

- Fecha, hora, materia, prioridad y estado: pendiente, en proceso o completada.
- Descripción, archivos adjuntos y fotos con la cámara.
- Se agrupan solas en atrasadas, hoy, mañana, esta semana y más adelante.
- Cuando te entregan la nota de un examen, la escribes ahí mismo y queda guardada en el periodo.
- Si completas o borras algo sin querer, puedes deshacerlo.

### Horario y calendario

- Horario por días, con la clase de ahora y la que sigue.
- Vista de la semana con las clases en bloques de colores.
- Calendario del mes con lo que tienes cada día.

### Panel de abajo

Siempre está a la vista y muestra la clase en la que estás o lo próximo que tienes. Al abrirlo aparece la lista de lo que sigue. El botón de play inicia un temporizador de estudio de 15, 25, 45 o 60 minutos.

### Recordatorios

Notificaciones antes de cada examen o entrega: a la hora, 1 hora, 3 horas, 1 día, 2 días o 1 semana antes. También puede avisar unos minutos antes de cada clase. Llegan aunque la app esté cerrada y se vuelven a programar si se reinicia el celular.

### Apuntes

Cada materia tiene sus apuntes, con fotos del tablero o del cuaderno.

### SAPRED

SAPRED no tiene una API pública, así que no hay sincronización automática. Lo que sí hace la app:

- Abre SAPRED dentro de la app y la sesión queda guardada.
- En la página de notas de una materia, el botón **Traer notas** lee lo que hay en pantalla y te deja escoger qué notas guardar, en qué materia y en qué periodo.
- Abre la app Sapred Go si la tienes instalada.

### Lo demás

- Tema oscuro, claro o automático, y cinco colores de acento.
- Copia de seguridad en un archivo, para pasar los datos a otro celular.
- En celulares de gama baja apaga sola las transparencias. También se pueden quitar las animaciones.
- Funciona desde Android 5.0 y no necesita servicios de Google, así que sirve en Huawei y otros celulares sin Play Store.

## Instalar

1. Descarga el APK desde la sección **Releases** de este repositorio.
2. Ábrelo en el celular. Si te lo pide, permite instalar apps de esa fuente.
3. Puede salir un aviso de Play Protect porque la app no viene de Play Store. Toca **Más detalles → Instalar de todas formas**.
4. Al abrirla, acepta las notificaciones para que te lleguen los recordatorios.

Si quieres verla con datos antes de poner los tuyos, en la pantalla de bienvenida está la opción **Explorar con datos de ejemplo**.

## Cómo se calcula la nota

Ejemplo con escala de 0 a 5, aprobando con 3.0:

| Periodo | Nota |
|---|---|
| 1 | 3.73 |
| 2 | 3.58 |
| 3 | 3.13 |
| 4 | ? |

Para que el promedio de los 4 dé 3.0, la suma tiene que ser 12. Ya llevas 10.44, así que en el cuarto periodo necesitas **1.56**.

Si en ese periodo ya tienes 3.4 en un quiz que vale 20%, te falta (1.56 − 0.68) ÷ 0.80 = **1.1** en el 80% que queda.

La nota necesaria se redondea hacia arriba, porque si necesitas 3.43 y las notas van con un decimal, tienes que sacar 3.5.
