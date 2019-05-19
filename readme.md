# Imagen de docker con Ubuntu, Wine, Metatrader, ZeroMq, VNC y Fluxbox

 
 ## Volumen con MetaTrader
 
 Desde Windows descargar el [instalador de MetaTrader4](https://download.mql5.com/cdn/web/metaquotes.software.corp/mt4/mt4setup.exe) y ejecutarlo. 
 
 Localiza la carpeta instalada, usualmente en *Program Files (x86)/*, y el archivo *terminal.exe*, el cual ejecutamos con el parametro */portable* desde terminal CMD, que previamente abriremos en modo adminstrador.
 
 Nos identificamos con la cuenta y el servidor deseado en MetaTrader.
 
 En opciones (aunque esto puede ajustarse usando el archivo *startup.ini*):
 
  - Habilitamos el auto-trading y la importación de DLL.
  - Habilitamos el One-click trading
  - Reducimos a 5000 el número máximo de barras en el chart.
 
 Cerramos el terminal de MetaTrader.
 
 En el directorio de MetaTrader se habrán creado varias carpetas nuevas al haberlo lanzado como *portable*. 

 Para poder usar ZeroMQ en MetaTrader debemos usar el conector desarrollado por Darwinex Labs, lo encontramos en su repositorio
[DWX ZeroMQ Connector { Python 3 to MetaTrader 4 }](https://github.com/darwinex/dwx-zeromq-connector). De la carpeta *dependencies* extraemos el contenido de *mql-zmq-master.zip*.

Copiamos las carpetas *mql-zmq-master/Include/Mql* y *mql-zmq-master/Include/Zmq* en la carpeta de MetaTrader que se creo anteriormente *MQL4/Include*.

 En el directorio *MQL4/Libraries*  copiamos los archivos *libsodium.dll* y *libzmq.dll* que se encuentran en el extraido *mql-zmq-master/Library/MT4*.
 
 Descarga del repositorio el archivo *DWX_ZeroMQ_Server_vX.Y.Z_RCx.mq4* y lo guardamos en el directorio *MQL4/Experts*.
 
 Copiamos el archivo *setup.ini* en el mismo directorio que *terminal.exe* y lo editamos para incluir nuestro usuario, password y servidor.
  
## Docker

 Modificar del docker-compose.yml para indicar el directorio
local de Darwinex_MT4 e inciar el contenedor con
 
 `docker-compose up`
 
  Se puede conectar con VNC usando la contraseña 3579  (se puede modificar en 
 el archivo run_mt.sh)

  
  
  
  
 
  
  
  
  
