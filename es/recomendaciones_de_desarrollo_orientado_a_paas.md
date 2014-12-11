# Recomendaciones de desarrollo orientado a PaaS

## Arquitectura
1. Orientar la arquitectura a un entorno PaaS.
1. En la medida de lo posible evitar utilizar el filesystem, por ejemplo evitar el uso de ficheros de configuración.
1. Recomendamos usar una base de datos externa para persistir las configuraciones globales como las particulares de cada aplicación.
1. Jerarquia de propiedades y sobreescritura.
1. Las propiedades deben soportar multiples versiones de una aplicación.
1. Evitar cambiar la configuración por defecto del servidor de aplicaciones.
1. Utilizar la variable global definida en todos los GEAR's que especifica el tipo de entorno (DEV,PRE,PRO) para configurar la aplicación. Para el caso de entornos distintos a OpenShift (Ej. Pruebas locales), la ausencia de dicha variable o su presencia con un valor vacío sería indicativo de un entorno de desarrollo local.
1. Disponer de un registro de servicios externos. De esta forma se tiene catalogados todos los servicos SOAP y REST de forma centralizada.
1. Intentar que la arquitectura sea ligera evitando empaquetar librerías que no son utilizadas.
1. Almacenar los logs de las aplicaciones en un repositorio central (OpenBus/Kafka). La arquitectura debería contemplar esta funcionalidad vía appender, siendo necesario estandarizar el layout del log.
1. Gestión dinámica del nivel de trazas. Permitir cambiar dinamicamente el nivel de las trazas.
1. Visualizar la versión de la arquitectura en el momento de inicio de la aplicación.
1. Exponer métricas de la arquitectura y de la aplicación vía JMX, usando el MBServer de la plataforma java.

## Organización de los proyectos
1. Generar artefactos con aplicaciones auto-contenidas.
1. Git/Maven: Separar en proyectos independientes las piezas lógicas de la solución.
1. Cada proyecto debe poseer un POM en la propia raíz que permita el lanzamienta tradicional, tanto manualmente como desde las herramientas de IC.
1. Las propiedades de configuración y construcción de Maven deben estar centralizadas para facilitar su mantenimiento.
1. El versionado de cada proyecto debe ser independiente, permitiendo la evolución separada de las distintas piezas.
1. Para dar soporte a multiples versiones activas de un mismo servicio se debe considerar, tanto en los contextos publicados como en los jerarquias de propiedades de configuración, el número de la versión del servicio.
1. Acortar nombres de carpetas y artefactos Maven, deslindarlos de nombres que pudiesen colisionar con esfuerzos de otros proyectos.

## Empaquetado de aplicaciones:
1. Las aplicaciones deben ser autocontenidas. El objetivo es evitar la personalización del filesystem, facilitando así el auto-escalado. 
1. Varias aplicaciones podrán compartir artefactos siempre y cuando se empaqueten en un EAR. 
7. GEAR.