## L:1 ##
net 8 microservices : DDD, CQRS, vertical / clean architecture

## PRIMERO TOCA EMPEZAR CON CONSEPTOS BASICOS  ##

¿que es un microservicio?
es una forma de construir un programa grande usando muchos programas pequeños 
EJEMPLO: supon que estas creando una aplicacion para vender motos en lugar de hacer solo un programa gigante que haga todo, lo divides en varios programas pequeños 
y cada uno se encarga de cada cosa como por ejemplo un programa pequeño para usuarios (registro e inicio de sesion)
otro para mostrar las motos 
otro para procesar los pagos
otro para guardar los pedidos 
cada uno de esos programas pequeños es un microservicio 

## ARQUITECTURA 
es la forma en la que se organiza el programa por dentro , no es el codigo como tal, si no como 
se acomodan todas las partes del programa para que funcionen bien 
EJEMPLO: piensa en una casa: antes de construir, un arquitecto hace un plano decide 
Donde va la cocina 
Donde va el baño 
Donde van los cuartos 
Donde va la sala
ese orden y organizacion es la arquitectura 
EJEMPLO UNA APLICACION 
una aplicacion puede tener partes como ; pantalla , logica, base de datos , la arquitectura decide como se conectan esas partes 
cuando utilizas microservicios, la arquitectura decide cuantos microservicios habra, que hara cada uno, como se comunican entre ellos 
la arquitectura del sofware es = la forma en que esta organizada un programa por dentro 

## patrones 
los patrones son formas recomendadas de hacer algo por que ya se sabe que funcionan bien 
es como cuando algien ya describio la mejor forma de hacer algo, y los demas programadores usan la misma forma 
EJEMPLO : imagina una receta de hacer pasta , si muchas personas la usan y siempre queda bien, esa receta se vuelve la forma recomendada 
en programacion es igual entonces un patron  es como una receta de muchos programadores usan para resolver un problema 

## bibliotecas 
las bibliotecas son codigos que ya esta hecho para que no tengas que programarlo desde cero 
en NET.8 hay muchas bibliotecas que ayudan a ; conectarse a base de datos, crear paginas, manejar usuarios 

## mejores practicas 
son formas recomendadas para programar que elcodigo quede bien echo 

## patrones de arquitectura de los microservicios 
son formas recomendadas de organizar y hacer  funcionar los microservicios dentro de una aplicacion
EJEMPLO: API gateway , es un punto de entrada unico para todos los microservicios 
en vez de que la aplicacion hable con muchos microservicios diferentes todo pasa primero por un solo lugar 
otro rmplo puede ser base de datos por cada microservicio 
cada microservicio tiene su propia base de datos 
no comparten la misma 
ejemplo base de datos de  microsercio de usuario, microservicio de compra, micro servicio de productos 
asi se evita que un servicio dañe datos de otro

## tipos de microservicio 
Microservicios de Dominio: Están diseñados para manejar un componente específico del negocio.
Por ejemplo, en una aplicación de comercio electrónico, podrías tener microservicios 
para manejar productos, pedidos y usuarios. Cada uno se enfoca en un aspecto particular de la aplicación.

Microservicios de Arquitectura: Estos son servicios que proporcionan características de infraestructura,
como autenticación, autorización, y gestión de servicios. Pueden ser responsables de la seguridad y
la comunicación entre otros microservicios.

Microservicios Transaccionales: Se encargan de procesos de negocio que requieren operaciones múltiples, 
como procesar un pedido que involucra inventario, pagos y envío. Aquí podrías aplicar patrones como Saga 
para manejar transacciones distribuidas.

Microservicios Asíncronos: Utilizan colas de mensajes o eventos para comunicarse, permitiendo una mayor
eficiencia y desacoplamiento. Por ejemplo, un microservicio que procesa pedidos podría generar eventos que otros 
microservicios consuman para llevar a cabo diferentes acciones, como la actualización de inventario o notificaciones al cliente.

Microservicios de Inteligencia: Estos microservicios pueden incluir servicios de análisis de datos, recomendaciones de productos,
y otros tipos de servicios que añaden inteligencia a la aplicación.

## como es el desarrollo de los microservicios 

  Comprender los Fundamentos: Comienza por entender qué son los microservicios, cómo funcionan y qué ventajas ofrecen en comparación con monolitos.
  Los microservicios son servicios independientes y autónomos que se comunican entre sí a través de APIs bien definidas.

Aprender un Lenguaje de Programación: Familiarízate con un lenguaje adecuado para el desarrollo de microservicios.
En el contexto de este curso, se utiliza C# y .NET, lo cual es una buena elección si ya tienes experiencia con estas tecnologías.

Explorar Patrones de Diseño: Investiga sobre patrones de arquitectura y diseño específicos para microservicios.
Esto incluye aprender sobre el diseño orientado al dominio (DDD), patrones como el mediador, proxy, y decorator,
así como el uso de API Gateway para la comunicación entre servicios.

Práctica del Desarrollo: Una vez que tengas la teoría, empieza a diseñar y desarrollar tus propios microservicios.
Puedes utilizar herramientas como Docker para la contenerización y orquestación de tus aplicaciones.

Realizar Pruebas y Aseguramiento de Calidad: Incorpora pruebas en tu desarrollo utilizando frameworks de pruebas como 
xUnit para garantizar que tus microservicios son robustos y funcionales.

## como un microservicio puede actualizar el microservicio existente sin tener que reconstruir y volver a desplegar toda la aplicacion

Despliegue Independiente: Cada microservicio tiene su propio código base y puede ser desplegado de forma independiente. Esto significa que un equipo de desarrollo 
puede actualizar un microservicio sin necesidad de afectar a otros servicios o al sistema en su conjunto.

API Bien Definidas: Los microservicios se comunican entre sí mediante APIs bien definidas. Esto permite que los desarrolladores realicen cambios en 
un microservicio sin afectar la funcionalidad de otros microservicios, siempre que la interfaz (API) permanezca intacta.

Estrategia de Versionado: Al actualizar un microservicio, es posible implementar una estrategia de versionado para gestionar diferentes versiones de la API,
permitiendo que las aplicaciones clientes sigan utilizando la versión anterior hasta que estén listas para adaptarse a los cambios.

Arquitectura Basada en Eventos: En algunos casos, se puede utilizar una arquitectura orientada a eventos, 
donde los cambios en un microservicio se comunican a otros servicios a través de eventos.
Esto permite a los servicios reaccionar a cambios sin necesidad de un despliegue completo.

Sistemas de Gestión y Automatización: Herramientas de gestión de configuración y automatización de despliegues, como Docker y Kubernetes, 
pueden ayudar a simplificar y gestionar el proceso de despliegue de microservicios, asegurando que las actualizaciones sean rápidas y efectivas.

## beneficios de la arquitectura 
Agilidad e Innovación: Permite un desarrollo más rápido y ágil de nuevas características, 
lo que reduce el tiempo de lanzamiento al mercado. Al ser servicios pequeños e independientes, 
es más sencillo gestionar correcciones de errores y actualizaciones sin necesidad de redeplegar toda la aplicación.

Escalabilidad Flexible: Los microservicios pueden escalarse de manera independiente, 
lo que significa que sólo los servicios que requieren más recursos pueden ser escalados sin necesidad de escalar toda la aplicación. 
Esto no sólo mejora la eficiencia en la utilización de recursos, sino que también es más costo-efectivo.

Equipos Pequeños y Enfocados: Cada microservicio puede ser gestionado por un pequeño equipo que se enfoca únicamente en un componente específico,
lo que facilita la especialización y la eficacia en la resolución de problemas relacionados con sus servicios.

Independencia Tecnológica: Los microservicios no requieren compartir la misma pila tecnológica. Esto proporciona flexibilidad para utilizar diferentes
lenguajes de programación, bases de datos y tecnologías según las necesidades específicas de cada servicio.

Resiliencia: La arquitectura de microservicios puede contribuir a la resiliencia del sistema.
Si un microservicio falla, los otros pueden seguir funcionando, minimizando el impacto en la aplicación general.

estos ofrecen una forma de de desarrolllar aplicaciones que son mas rapidas de construir mas siples 
de manteener y faciles de escalar 

## cuales son los distintos retos y desventajas de la arquitectura de los micoservicios que se deben considerar

Complejidad Aumentada: A medida que se descompone una aplicación en múltiples microservicios, la complejidad de gestión también aumenta. 
Cada microservicio es más simple, pero la interfaz entre todos ellos puede volverse complicada, 
y la coordinación de despliegues se hace más difícil, especialmente en sistemas grandes con muchos servicios.

Problemas de Red y Latencia: Los microservicios dependen de la comunicación a través de la red, lo que puede dar lugar a problemas de red y latencia.
Cuando un servicio necesita comunicarse con otros para completar una solicitud,
esto puede resultar en tiempos de respuesta más lentos y en la necesidad de diseñar adecuadamente las API para evitar llamadas excesivas entre servicios.

Desafíos de Versionado y Despliegue: Cada microservicio tiene su propio ciclo de vida de despliegue y versionado, lo que puede generar 
complicaciones si no se gestionan correctamente.
Es fundamental tener una estrategia efectiva para gestionar las versiones de API y coordinar las actualizaciones de servicios interdependientes.

Requerimientos de DevOps: La implementación de microservicios a menudo exige una infraestructura DevOps sólida y herramientas adecuadas para automatizar despliegues,
monitoreo y gestión de servicios. Sin una infraestructura bien establecida, el manejo de microservicios puede volverse ineficiente y propenso a errores.

Dificultades de Monitoreo y Depuración: Identificar y solucionar problemas en una arquitectura de microservicios puede ser más
complicado que en una arquitectura monolítica,
debido a la distribución de componentes y la variedad de tecnologías utilizadas en diferentes microservicios.





## develop vertical slice feacture folder with CQRS  and mediatR

explica como desarrollar carpetas de caracteristicas de corte vertical con circulos y mediador 




















