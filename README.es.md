<!--hide-->
# Sistema de gestión de filas SMS
<!--endhide-->

Permite crear un sistema de filas: el sistema de filas se utiliza en gran medida en las instituciones gubernamentales, aeropuertos, bancos y muchos otros lugares que buscan organizar el tráfico entrante.

Los sistemas de fila también se pueden usar para equilibrar la carga de diferentes aplicaciones como:

- Establecimiento de prioridades en las solicitudes entrantes de servidores web.
- Inmigración y solicitudes de visa que deben ser priorizadas.
- Paquetes de red.
- etc.


## 🌱  Cómo iniciar este proyecto

 No clones este repositorio. El primer paso para comenzar a codificar es clonar el [flask boilerplate](https://github.com/4GeeksAcademy/flask-rest-hello) en tu computador local o con Gitpod.

a) Si usas Gitpod (recomendada) puedes clonar el boilerplate [clic aquí](https://github.com/4GeeksAcademy/flask-rest-hello).

b) Si trabajas localmente, escribe el siguiente comando en tu terminal: 
```sh
git clone  git clone https://github.com/4GeeksAcademy/flask-rest-hello
```
💡 Importante: Recuerda actualizar el `remote` del proyecto con el de tu repositorio usando `git remote set-url origin <your new url>`, y luego guardar tu código en tu nuevo repositorio usando `add`, `commit` y `push`.


## 📝 Instrucciones

+ La API debe integrarse con Twilio para poder enviar SMS para notificar a los usuarios cuando llegue su turno.
+ Crea una API que permita a los clientes administrar una fila simple, usa la siguiente estructura de datos para implementar la fila:

```py
class Queue:

    def __init__(self):
        self._queue = []
        # depending on the _mode, the queue has to behave like a FIFO or LIFO
        self._mode = 'FIFO'

    def enqueue(self, item):
    def dequeue(self):
    def get_queue(self):
    def size(self):
        return len(self._queue)
```

## Ejemplo de Flujo de Trabajo

1. La API recibe una solicitud para agregar a Bob a la fila (`POST / new`) con cualquier prioridad particular (FIFO o LIFO).
2. La API agrega a Bob y le notifica con un SMS de confirmación, el SMS debe indicar cuántas personas están frente a él en la línea.
3. El sistema ahora espera hasta que el endpoint `GET / next` se ejecute para procesar a la persona en la fila.
4. Cada vez que se recibe una solicitud `GET / next`, la siguiente persona en la fila se procesa hasta que sea el turno de Bob.
5. Cuando Bob es procesado, el sistema le envía otro SMS para avisarle que ha llegado su turno y lo elimina de la lista.

## Más Detalles

1. Tú debes crear 3 endpoints para tu API:

- POST `/new`: Recibirá información sobre un usuario y lo agregará a la fila.
- GET `/next`: Se procesará un punto de la fila.
- GET `/all`: Devolverá una lista con todos los que estén pendientes de ser procesados (la fila actual).

## 📖 Fundamentos

Este ejercicio te hará practicar los siguientes fundamentos:

1. Aquí puedes encontrar información sobre [como enviar un sms con twillio](https://www.twilio.com/docs/sms/send-messages), tendrás que registrarse y crear una cuenta (gratis) y también registrar un número (gratis)
4. Construir RESTful API
5. Estructuras de datos complejas.
6. Queue (FIFO vs FILO)
7. SMS.
