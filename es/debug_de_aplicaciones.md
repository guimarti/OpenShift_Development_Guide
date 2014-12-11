# Debug de aplicaciones

1. Crear el marker **enable_jpda**.

    `touch .openshift/markers/enable_jpda`
    
1. Actualizar la aplicación ( por git push o despliegue binario )

1. Hacer port-forward de la aplicación

    `rhc port-forward -a <app_name>`
    
1. Comprobar que se habilita el puerto **8787**

        $ rhc port-forward -a <app_name>
        Checking available ports ... done
        Forwarding ports ...
        
        To connect to a service running on OpenShift, use the Local address
        
        Service Local               OpenShift
        ------- -------------- ---- -----------------
        java    127.0.0.1:3528  =>  127.7.33.129:3528
        java    127.0.0.1:4447  =>  127.7.33.129:4447
        java    127.0.0.1:5445  =>  127.7.33.129:5445
        java    127.0.0.1:5455  =>  127.7.33.129:5455
        java    127.0.0.1:7600  =>  127.7.33.129:7600
        java    127.0.0.1:8080  =>  127.7.33.129:8080
        java    127.0.0.1:8787  =>  127.7.33.129:8787
        java    127.0.0.1:9990  =>  127.7.33.129:9990
        java    127.0.0.1:9999  =>  127.7.33.129:9999

1. En Eclipse, abrir *Debug Configurations > Remote Java Application*

1. Seleccionar el proyecto con el código fuente desplegado en la aplicación.

1. Seleccionar el host y el puerto:
        
        Host : 127.0.0.1
        Port : 8787