# Instalación rhc

Instalar rhc: `$> gem install rhc`

> Si el proceso falla por algo del tipo `unknow host http://rubygems.org....` , significa que no tienes conexión con el repositorio 
  de gemas y necesitarás descargarlas a mano. Las gemas necesarias son:
```
Gem rhc-1.33.4
  archive-tar-minitar (>= 0)
  commander (>= 4.0)
  highline (~> 1.6.11)
  httpclient (>= 2.4.0)
  net-scp (>= 1.1.2)
  net-ssh (>= 2.0.11)
  net-ssh-multi (>= 1.2.0)
  open4 (>= 0)
```
Una vez descargadas todas las gemas, colocarlas todas en el mismo directorio y ejecutar el comando en dicho directorio `$> gem install rhc`