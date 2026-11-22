# Tarea: Mi prompt avanzado

## Tarea elegida

 - Crear un menu para actualizar una tabla mysql con python

## Version 1: prompt basico

```text
crea un menu en python para actualizar una tabla mysql con python
```
## Version 2
 - Paso 1
```text
voy a crear una aplicacion para ingresar productos en una tabla de inventario de una base de datos mysql, indica los rquisitos mas importantes a considerar
```
 - Paso 2
```text
Con los requisitos mencionados diseña las clase necesarias con sus principales atributos, utiliza el lenguaje python
```
 - Paso 3
```text
Escribe el codigo python para la clase Producto, con su constructor, atributos  y metodos
```
 - Paso 4
```text
Revisa el codigo del conector a la base de datos para que el usuario y contraseña utilicen caracteres no solo letras y  numeros. Propone 3 mejoras para evitar ataques por inyeccion DOS
```

## Version 3: prompt final
```text
<rol>
Actúa como un programador senior especializado en codigo Python y bases de datos MySQL, con conocimientos avanzados en creacion de interfaz de línea de comandos.
</rol>
<contexto>
Necesito una aplicación por consola para administrar y actualizar el inventario de componentes electrónicos de mi taller.
Los componentes incluyen categorías como resistencias, condensadores, transistores, circuitos integrados, con diferentes subcategorias (por ejemplo: resistencias de carbón, de 1/4W, de 1/2W; condensadores electrolíticos, cerámicos, de tantalio, circuito 7400, 4011, etc).
Toda la información debe guardarse en una base de datos MySQL.
</contexto>
<tarea>
Diseña y escribe el código completo de una aplicacion de consola interactiva que permita:
Crear si no existe la tabla o tablas en MySQL.
Registrar nuevos componentes discretos y actualizar los existentes (por ejemplo, sumar o restar stock, valor, tipo, caja, etc).
Consultar, buscar y listar componentes (por ID, categoría, tipo o texto) para ubicar fácilmente y saber cual registro actualizar.
Opcionalmente eliminar registros obsoletos o erróneos con confirmación previa.
</tarea>
<datos>
Estructura base sugerida para los componentes discretos (considera mejorala segun el diseño):
- id: identificador único autoincremental
- categoria: ejemplo "Resistencia", "Condensador", "Diodo", "Transistor", "Inductor", "Circuito Integrado"
- tipo: ejemplo "Carbón", "Película metálica", "Electrolítico", "Cerámico", "Tantalio"
- valor: ejemplo "10k ohm", "100nF", "10uF". "7404"
- especificacion: ejemplo "1/4W 10PPM", "1/2W 5%", "50V", "16V"
- stock: entero
- Ubicacion: ejemplo "caja 01"
- notas: texto opcional (encapsulado, tolerancia, polaridad, usado, nuevo, etc.)
- actualizado: timestamp de última actualización
</datos>
<ejemplo>
Flujo esperado en consola al actualizar stock:
- El usuario elige la opción "Actualizar componente" en el menú principal.
- Puede buscar por ID o filtrar por categoría o tipo (ej. "Condensador" / "Electrolítico") o una palabra contenida.
- Ingresa el ID del componente con opcion de actualizar la cantidad como suma o resta, ejemplo: "-10, usado en un proyecto".
- Mostrar un resumen del cambio antes de confirmar el cambio.
</ejemplo>
<restriciones>
- Solo usar componentes electrónicos discretos, no de tipo complejo como displays, modulo de sensores, modulos de entrenamiento o desarrollo.
- La interfaz debe ser clara y facil de usar.
</restriciones>
<formato>
Entrega la solución organizada en:
1. Consultas SQL para la base de datos y tabla(s).
2. Modulo en codigo python con clases.
</formato>
<validacion>
Verifica que:
- El código debe cubrir la inserción de nuevos componentes y actualización de registros existentes.
- La contraseña y nombre de usuario de la base de datos Mysql permita el uso de simbolos ademas e los alfanumericos ($, %, #, @, etc).
</validacion>
```

## Tecnicas usadas en el prompt final

El prompt es un prompt estructurado, en la tabla se muestra las diferentes tecnicas usadas:
| Etiqueta | Tecnica | Fragmento |
|---|---|---|
| `<rol></rol>` | **Role Prompting**  | Actúa como un programador senior especializado en código Python y bases de datos MySQL, con conocimientos avanzados en creación de interfaz de línea de comandos. | 
| `<tarea></tarea>` | **Chain of Thought** y **Descomposición** | Diseña y escribe el código completo de una aplicacion de consola interactiva que permita:<ul><li>Crear si no existe la tabla o tablas en MySQL.</li><li>Registrar nuevos componentes discretos y actualizar los existentes (por ejemplo, sumar o restar stock, valor, tipo, caja, etc).</li><li>Consultar, buscar y listar componentes (por ID, categoría, tipo o texto) para ubicar fácilmente y saber cual registro actualizar.</li><li>Opcionalmente eliminar registros obsoletos o erróneos con confirmación previa.</li><ul>|
| `<ejemplo></ejemplo>` | **Few-shot** | Flujo esperado en consola al actualizar stock:<ul><li>El usuario elige la opción "Actualizar componente" en el menú principal.</li><li>Puede buscar por ID o filtrar por categoría o tipo (ej. "Condensador" / "Electrolítico") o una palabra contenida.</li><li>Ingresa el ID del componente con opcion de actualizar la cantidad como suma o resta, ejemplo: "-10, usado en un proyecto".</li><li>Mostrar un resumen del cambio antes de confirmar el cambio.</li><ul>|
| `<formato></formato>` | **Descomposición** | Entrega la solución organizada en:<ol><li>Consultas SQL para la base de datos y tabla(s).</li><li>Modulo en codigo python con clases.</li><ol>|
| `<validacion></validacion>` | **Autocrítica** | Verifica que:<ul><li>El código debe cubrir la inserción de nuevos componentes y actualización de registros existentes.</li><li>La contraseña y nombre de usuario de la base de datos Mysql permita el uso de simbolos ademas e los alfanumericos ($, %, #, @, etc).</li><ul>|

## Evaluacion del resultado

| Qué revisar |Cumple (Sí / No) |
|---|---|
| ¿Tiene script para la creacion de la base de datos y tablas? | Si |
| ¿Muestra la estructura del proyecto? |  Si |
| ¿Crea el modulo de conexion a la base de datos? | Si |
| ¿Crea los modulos de las clases? | Si |
| ¿Verifica que el usuario y contraseña permita el uso de caracteres especiales? | Si |

## Por que elegi estas tecnicas

Poruqe estoy describiendo lo que mi aplicacion necesita, tambien se proporciona el contexto, los dato, la funcionalidad y el formato de entrega.