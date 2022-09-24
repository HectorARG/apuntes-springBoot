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