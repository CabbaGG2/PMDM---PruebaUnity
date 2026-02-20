# Prueba de Unity

## Comportamiento del jugador
- Se realizaron los objetos en la escena, se creo el plano, las paredes y los actores (player y enemigo)
- Se le agregó movimiento al player implementando el componentes player input y el rigidboy.
- Se declaran las variables rigidBody y las 2 variables float que seran el movimiento del jugador en las coordenadas x y z.
- Se implmentó una variable pública de velocidad para lograr que la velocidad se pueda modificar desde Unity.
- se inicializa el componentes RigidBody en el metodo Start.
- en el metodo OnMove recibimos como parametro un inputValue el cual se utilizará para conseguir un vector2 el cual aplicará la fuerza y le asignará el nuevo valor de los vectores a las dos variables float declaradas anteriormente las cuales seran las coordenadas del jugador.
- en el metodo FixedUpdate Se declara una variables Vector3 el cual recibe como valores los dos movimientos que conseguimos anteriormente en el metodo OnMove.
- a la variable del RigidBody utilizamos su metodo interno "AddForce" el cual le aplica la variable del Vector3 que acabamos de conseguir multiplicado por la velocidad que asignemos.

## Comportamiento con las colisiones
- Utilizando la función OnCollisionEnter podemos decirle al actor que tenga el script asignado que si entra en colisión con otro objeto o actor realice alguna acción.
- En este caso utilizamos los "Tag" para que el actor identifique que colisionó con un "Enemigo" y muestre un mensaje por consola.
- utilizando las coordenadas podemos tambien avisar por consola si el enemigo esta cerca o lejos.

## Comportamiento del enemigo
- Para aplicarle IA al enemigo utilizamos la tecnologia del NavMesh
- primero le aplicamos un NavMeshSurface al suelo para que el agente identifique cual es su playground.
- luego le asignamos al objeto que asignemos como enemigo el componentes NavMeshAgent.
- Realizamos su script en el cual tenemos que importar las librerías de IA de Unity y declaramos la vcariables NavMeshAgent y lo inicializamos en la función Start.
- Como queremos que el enemigo su comportamiento sea seguir al jugador, en la función Update le decimos al agente que utilice el metodo SetDestination y vaya a la posición del jugador que será una variable publica que asignemos en Unity. 
