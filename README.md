# Socket_Ibero
Actividad de Arquitectura de Software
=======
# Proyecto de Autenticación de Usuario

Sistema de validación que permite a los usuarios iniciar sesión mediante un documento de identificación de usuarios registrados en una base de datos y en base a esto se realiza la ejecución o el cierre del programa. El aplicativo está compuesto por un servidor(serverdeploy.py) y un cliente (cliente.py) que se comunican a través de sockets, lo que permite la comunicación y respuesta entre el cliente y el servidor. Además se le implementan hilos para permitir la conexion de varios clientes al tiempo en el servidor.

# Estructura

- **serverdeploy**.py: Se importa el modulo de socket (permite abrir la comunicación cliente - servidor) para trabajar con dicha librería, se establece la conexion a la direccion del servidor (en este caso sería localhost y el puerto). Se crea un objeto que va a ser el encargado de recibir y enviar la información del usuario al servidor. Se valida la opcion para aceptar la conexion mediante el metodo accept y en caso de que el usuario coloque un documento no registrado tendrá dos opciones mas y si no logra ingresar el servidor se cerrará (lo anterior se establece mediante un ciclo While para validar los intentos).
Se importa threading para el manejo de hilos y habilitar el uso de varios clientes al tiempo. (Adicionalmente se le coloca un contador para verificar la cantidad de clientes conectados y cuando no detecte clientes el servidor cierre la sesion.)
Una vez validado el usuario, con el metodo send. El servidor informará al usuario que se ha conectado satisfactoriamente y podrá enviar mensajes al servidor gracias al metodo recv hasta que la sesion sea terminada por el mismo usuario al escribir "salir"

- **cliente.py**: Archivo que facilita la interaccion con el servidor usando socket.AF_INET para el intercambio de datos y socket.SOCK_STREAM para evitar perdida de datos de información del cliente al servidor. Desde aquí el usuario puede validar si existe en la base de datos y tiene acceso al servidor.

- **dbplanilla.py**: Diccionario con datos de documentos y nombre de los usuarios autorizados a iniciar sesión.
- **usuarios.py**: archivo con una función principal que permite validar a los usuarios del sistema.

## Requisitos

- Python
- Interacción por consola

## Instalación

1. Clonar el repositorio en la carpeta de preferencia


## Uso

### 1. Ejecutar del programa

1. Ejecutar dos consolas dentro de la carpeta
2. En la consola 1 colocar python serverdeploy.py (Para iniciar el servidor)
3. En la consola 2 colocar python cliente.py (Para iniciar la validación de los usuarios)

### Integrantes del proyecto
- Diego Alejandro Cuartas Duque
- Juan José Cardona Ramírez
- Carlos de Jesús Ochoa Jiménez
