**¿Qué es una dependencia?
Pequeña característica de un objeto especifico, que puede impactar de manera particular en el funcionamiento de una unidad.
Por ejemplo, las dependencias de un Smartphone serian:
Cámara
Micrófono
Pantalla
Batería

Alta cohesión: Involucra que la entidad ejecute sus acciones sin involucrar otra clase o entidad.
Bajo acoplamiento Hablamos de acoplamiento bajo cuando existe una independencia entre los componentes entre si, por el contrario un 
alto acoplamiento es cuando tenemos varias dependencias relacionadas a un solo componente.
Entonces podemos afirmar que en la definición de un buen diseño de software se debe tener una ALTA COHESIÓN y un BAJO ACOPLAMIENTO.

**Qué es un bean? 
Un bean básicamente son módulos desarrollados en Spring estos se encargan de brindarnos toda la lógica que necesitamos para nuestra aplicación. Ejemplo: Si necesitamos referenciar que nuestra clase es un modelo hacemos uso de el bean @entity . Esto nos permite usar propiedades creadas para este tipo de modulo que nos agilizan nuestro desarrollo. Al hacer inversión de control nosotros al llamar esos beans lo que hacemos es referenciar módulos funcionales creados por spring. Spring boot nos facilita el fácil instanciamiento de estos a nuestra aplicación, haciendo todo por nosotros…

**Hay 3 formas de aplicar la inyeccion de dependencias:
-Por medio de atributo
-Por medio de metodos sets
-El mas famoso es por medio de constructor.

**AUTOCONFIGURACION Y RUNTIME
Configura automáticamente tus aplicaciones basadas en dependencias JAR que agregaste mediante el pom.xml, pero si nosotros realizamos una configuración manual esta es priorizada por Spring Boot.

**¿QUE ES UNA ANOTACION EN SPRING BOOT?
Una Anotación es una forma de añadir metadatos al código fuente Java que están disponibles para la aplicación en tiempo de ejecución o de compilación. Es una alternativa mas sencilla al uso de XML.

**TIPOS DE ANOTACIONES
@Controller: Para indicar que esta será la clase que gestionara las peticiones del usuario por get, post, put, patch o delete.
@Service: Con esta notación especificamos que en esta clase se encontrara toda nuestra lógica de negocio, cálculos o llamadas a otras API externas.
@Repository: Se usa para las clases o interfaces que funcionaran con el acceso a la base de datos.
Si nuestra clase o interfaz no tiene una especificación clara como @Service, @Repository o @Controller, simplemente recurrimos a @Component y le indicamos que sencillamente es un componente.
Por otro lado, no es estrictamente necesario que cumplas con colocar una notación especifica, pero es una buena practica.

**Anotaciones para indicar dependencias en Spring Boot
@Component: anotación genérica, de ella nacen las siguientes (@Controller, @Service y @Repository). Se usa cuando tenemos una clase abstracta.
@Controller: la usamos en las clases que se encargarán tanto de recibir las peticiones HTTP por parte de la parte frontal como devolver las respuestas de esas peticiones procesadas al frontal.
@Service: la usamos en las clases que implementamos la lógica de negocio, es decir, dónde realizamos las validaciones.
@Repository: la usamos en interfaces (no clases), donde nos ocuparemos de la obtención y persistencia de datos.

**¿QUE ES UNA ANOTACION EN SPRING BOOT?
Una Anotación es una forma de añadir metadatos al código fuente Java que están disponibles para la aplicación en tiempo de ejecución o de compilación. Es una alternativa mas sencilla al uso de XML.
TIPOS DE ANOTACIONES
@Controller: Para indicar que esta será la clase que gestionara las peticiones del usuario por get, post, put, patch o delete.
@Service: Con esta notación especificamos que en esta clase se encontrara toda nuestra lógica de negocio, cálculos o llamadas a otras API externas.
@Repository: Se usa para las clases o interfaces que funcionaran con el acceso a la base de datos.
Si nuestra clase o interfaz no tiene una especificación clara como @Service, @Repository o @Controller, simplemente recurrimos a @Component y le indicamos que sencillamente es un componente.
Por otro lado, no es estrictamente necesario que cumplas con colocar una notación especifica, pero es una buena practica.

**Un articulo que explica mejor la implementacion de los parameters, ya que aca solo nos dice como funciona, mas no en que caso emplear este tipo de Query.
Se usa principalmente para renombrar esos distintos atributos de nuestra entidad DTO ya que esta entidad esta compuesta por atributos foraneaos de 2 o mas tablas, tambien es importante saber su cardinalidad y nombrarla con la anotacion correspondiente @JoinColumn donde hago referencia a que mi entidad DTO tiene columnas de varias tablas,
Respecto a lo anterior al yo declarar un parametro dentro de la consulta, asi hago referencia a un atributo en especifico, para mejorar la segurdad del atributo hubiera sido de ayuda que en ves de emplear un constructor, empleemos un metodo get, y asi encapsulandolo evitamos un error por inyeccion de JPQL

**¿Para qué usar una transacción?
El objetivo de una transacción es ejecutar todas las líneas de código de nuestro método y guardar finalmente la información en un repositorio, por ejemplo en nuestro caso, una base de datos. Esto se conoce como commit de nuestra transacción.
Si por alguna razón algo fallara en nuestro método de Servicio, se daría marcha atrás a los cambios realizados en la base de datos. Esto se conoce como rollback.
Lo anterior permite que nuestra información, ya sea que se una única base de datos o no, esté íntegra, y no exista posibilidad de datos corruptos por errores o fallas en la ejecución de nuestros métodos Java.

**Las características de una transacción tienen el acrónimo ACID:
Atomicidad: Las actividades de un método se consideran como una unidad de trabajo. Esto se conoce como Atomicidad. Este concepto asegura que todas las operaciones en una transacción se ejecuta todo o nada.
Si todas las instrucciones o líneas de código de un método transaccional son ejecutadas con éxito, entonces al finalizar se realiza un commit, es decir, guardado de la información.
Si alguna de las instrucciones falla se realiza un rollback, es decir, ninguna de la información es guardada en la base de datos o el repositorio donde ser persiste dicha información…
Consistente: Una vez que termina una transacción (sin importar si ha sido exitosa o no) la información queda en estado consistente, ya que se realizó todo o nada, y por lo tanto los datos no deben estar corruptos en ningún aspecto.
Aislado: Múltiples usuarios pueden utilizar los métodos transaccionales, sin afectar el acceso de otros usuarios. Sin embargo debemos prevenir errores por accesos múltiples, aislando en la medida de lo posible nuestros métodos transaccionales. El aislamiento normalmente involucra el bloqueo de registros o tablas de base de datos, esto se conoce como locking…
Durable: Sin importar si hay una caída del servidor, una transacción exitosa debe guardarse y perdurar posterior al termino de una transacción.