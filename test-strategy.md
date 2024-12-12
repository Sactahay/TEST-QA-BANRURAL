Test Strategy Document

Problemas Encontrados y Soluciones

Problema 1: Generación del Número Aleatorio Incorrecta

Causa: El código original generaba un número aleatorio con Math.random() * 10, lo cual solo generaba valores entre 0 y 10, y no incluía el rango completo de 1 a 100.

Solución: Se corrigió la lógica a Math.floor(Math.random() * 100) + 1 para garantizar un número aleatorio entre 1 y 100.

Problema 2: Referencias Incorrectas a Elementos del DOM

Causa: La clase .lowOrHi estaba mal referenciada (faltaba el punto).

Solución: Se ajustó la referencia correcta utilizando document.querySelector('.lowOrHi').

Problema 3: Evento Mal Registrado

Causa: Se utilizó addeventListener en lugar de addEventListener, lo cual causaba que los clics en el botón no ejecutaran el evento.

Solución: Se corrigieron todos los casos de addeventListener por addEventListener.

Problema 4: Mensajes y Colores Incorrectos

Causa: Los mensajes y colores mostrados no seguían las reglas establecidas, como "Felicitaciones" para ganar y "Incorrecto" en otros casos.

Solución: Se revisó y ajustó la lógica para que cumpla con los requerimientos.

Problema 5: Validación de Entrada

Causa: No se validaban los valores ingresados por el usuario, lo cual permitía valores no numéricos.

Solución: Se agregó validación para convertir la entrada a un número utilizando Number().

Plan de Pruebas

Pruebas de Entrada

Escenarios:

Ingresar valores fuera del rango (por ejemplo, 0 o 101).

Ingresar valores no numéricos (por ejemplo, "texto").

Resultado Esperado: Mostrar mensajes de error o ignorar la entrada sin afectar los intentos restantes.

Pruebas de Comparación del Número

Escenarios:

Ingresar un número menor al generado.

Ingresar un número mayor al generado.

Adivinar el número correctamente.

Resultado Esperado: Mostrar mensajes adecuados ("El número es mayor", "El número es menor", "Felicitaciones").

Pruebas de Límites de Intentos

Escenarios:

Agotar los 10 intentos sin adivinar el número.

Adivinar el número en el último intento.

Resultado Esperado: Mensajes adecuados ("¡Pérdistes!" o "Felicitaciones") y bloqueo del formulario.

Pruebas de Reinicio del Juego

Escenarios:

Presionar el botón de reinicio.

Resultado Esperado: Todos los campos se reinician, el contador de intentos vuelve a 1 y se genera un nuevo número aleatorio.
