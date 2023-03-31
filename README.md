Sistemas Operativos II - Laboratorio II IPC
###  Ingeniería en Computación - FCEFyN - UNC - 2023
# Laboratorio 2 - Interprocess Communication Advanced

## Introducción
Continuando el estudio de los mecanismos de IPC que vimos en el Laboratorio I, ahora haremos uso del más utizado: sockets.

## Objetivo
El objetivo del presente trabajo práctico es que el estudiante sea capaz de diseñar e implementar un software que haga uso de los mecanismos de IPC que provee el Sistema Operativo, implementando lo visto en el teórico, práctico y haciendo uso todos los conocimientos adquiridos en Ingeniería de Software y Sistemas Operativos I y los desarollado en el Laboratorio I.

## Desarrollo
Se pide que diseñe, implemente y testee un conjunto de aplicaciones (desarrollado en lenguaje C) de una arquitectura cliente servidor de tres capas que implemente y soporte al menos 3 protocolos de la familia descriptas en  <sys/socket.h>.

### Clients
Se deben implementar tres tipos de clientes, los cuales se pueden instanciar un número N de veces.
- Cliente A: Debe poseer una cli, donde el usuario escribe un string, en formato a definir, que interactúe con [journalctl][jctrl], e imprime en pantalla el resultado.
- Cliente B: Debe poseer una cli, igual que el el Cliente A, pero recibe un archivo comprimido con el resultado.
- Cliente C: Un informe con: 
  - Memoria libre en el sistema
  - Load normalizado del sistema

### Server
- Debe cumplir con los requerimientos del Laboratorio I 
- Debe gestionar las conexiones y desconexiones de los clientes. 
- Es el encargado de comunicar los mensajes de los usuarios y responder según corresponda.
- La lógica y diseño de funcionamiento, es tarea de los estudiantes.

## Criterios de Corrección
- Se debe compilar el código con los flags de compilación: 
     -Wall -Pedantic -Werror -Wextra -Wconversion -std=gnu11
- La correcta gestion de memoria.
- Dividir el código en módulos de manera juiciosa.
- Estilo de código.
- Manejo de errores
- El código no debe contener errores, ni warnings.
- El código no debe contener errores de cppcheck.
- El estudiante debe proveer un script para validar los requerimientos del proyecto.

## Consideraciones
- Los clientes son _lightweight_. Es decir, todo el procesamiento se hace del lado del servidor.
- Los clientes deben validar el checksum de lo recibido.
- La descarga del archivo debe funcionar para cualquier tamaño/formato.
- En caso de que ocurra una falla del lado del servidor durante el procesamiento de la solicitud, se deberá informar al cliente antes de cerrar la conexión.
- Todos los mensajes entre el servidor y el cliente deben ser de formato [json][jsonf]

## Entrega

La entrega se hace a través del repositorio de GitHub y se deberá demostrar la realización del mismo mediante un correcto uso del [workflow de Git][workflow]. El repositorio deberá proveer los archivos fuente y cualquier otro archivo asociados a la compilación, archivos  de  proyecto  ”Makefile”  y  el  código correctamente documentado. No debe contener ningún archivo asociado a proyectos de un IDE y se debe asumir que el proyecto podrá ser compilado y corrido por una `tty` en una distribución de Linux con las herramientas típicas de desarrollo. También se deberá entregar un informe (que pude ser en MD en el repo) explicando paso a paso el desarrollo, incluyendo gráficos del diseño solución propuesto, justificando en todo momento lo implementado.

## Evaluación
El presente trabajo práctico es individual y deberá entregarse antes de las 14:55ART del día 13 de Abril de 2023 dejando asentado en el LEV con el archivo de informe. Será corregido y luego se coordinará una fecha para la defensa oral del mismo.



[jctrl]: https://www.man7.org/linux/man-pages/man1/journalctl.1.html
[jsonf]: https://github.com/DaveGamble/cJSON
