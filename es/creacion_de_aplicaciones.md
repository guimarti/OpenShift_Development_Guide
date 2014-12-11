# Creación de aplicaciones

> **Atención:** se recomienda leer el libro de iniciacion a Openshift ([descarga](https://www.openshift.com/promotions/ebook)).

Se pueden crear aplicaciones utilizando 3 metodos:
* [Consola Web](#consola-web)
* [OpenShift Client rhc](#openshift-client-rhc)
* [Eclipse IDE Plugin](#eclipse-ide-plugin)

## Consola Web

1. Ir a la pestaña **Applications**
2. Pulsar el boton **Add Application...**
3. Seleccionar el tipo de cartucho principal.
4. Elegir un nombre y un dominio para la aplicación.
5. Opcional. Si el código fuente de la aplicación esta en un repositorio se puede indicar.
6. Seleccionar el tamaño del gear.
7. Seleccionar si se quiere o no una aplicación escalable.
8. Pulsar el boton **Create Application**

## OpenShift Client rhc

Utilizar el siguiente comando:

    $> rhc app create [args]
    
    args :
        -a <app_name>       ->  nombre de la aplicación
        -n <domain_name>    ->  nombre del dominio
        -t <web_cartridge>  ->  web cartridge que se va a utilizar
        -s                  ->  (opcional) aplicación escalable
        -c <cartridge_name> ->  (opcional) nombre del cartucho embebido (ejem, base de datos Postgresql).

## Eclipse IDE Plugin

1. Boton derecho sobre la cuenta de OpenShift : _New > Application.._
2. Seleccionar _Create a new OpenShift application_
3. Seleccionar un _Basic Cartridges_ y pulsar **Next**
4. Seleccionar un dominio.
5. Escribir el nombre de la aplicación.
6. Seleccionar el tamaño del Gear.
7. Seleccionar si se quiere que la aplicación sea escalable.
8. Añadir si se desea uno o varios Cartridges embebidos.
9. Finalizar el proceso.


