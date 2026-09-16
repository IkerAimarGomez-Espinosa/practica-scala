## Entorno 1

Para instalar Jupyter podermos encontrar información en la web: https://jupyter.org/install
Como esta indica ejecutamos el comando "pip install jupyterlab" en nuestro cmd, que comprobará si tenemos todo lo requerido para jupiter y los instalará si no los tenemos.
Una vez instalado jupyter, hay que usar el comando "jupyter lab" en nuestro cmd, el cual abrirá http://localhost:8888/lab en nuestro navegador, desde donde podremos trabajar con jupyter
Para instalar almond, entraremos en https://almond.sh/ y haremos click en la opción de install, eso nos llevará a https://almond.sh/docs/quick-start-install.
Te indica que debes tener instalado Java 1.8.0_121, yo ya lo tengo instalado pero en caso de no tenerlo, te proveé del enlace para descargarlo.
Antes de instalar almond debes de instalar coursier, en la página web indica que hay que usar los comandos:

- bitsadmin /transfer downloadCoursierCli https://git.io/coursier-cli "%cd%\coursier"
- bitsadmin /transfer downloadCoursierBat https://git.io/coursier-bat "%cd%\coursier.bat"

A mi no me han funcionado, y con ayuda de la IA, se que es por que no son comandos actualizados, en su lugar yo usaré:

- curl -fLo cs-x86_64-pc-win32.zip https://github.com/coursier/launchers/raw/master/cs-x86_64-pc-win32.zip

Extraigo el zip en la carpeta donde lo he descargado.
Aunque no sea obligatorio por consejo de la IA, voy a renombrar lo extraido (cs-x86_64-pc-win32.exe) a cs.exe para mayor comodidad a la hora de ejecutar comandos con:
move cs-x86_64-pc-win32.exe cs.exe
Ahora que ya tengo correctamente instalado coursier, puedo instalar almond con

- .\cs launch --use-bootstrap almond -M almond.ScalaKernel --scala 2.12.21 -- --install

Es importante que despues de "almond.ScalaKernel", separado con un espacio se escriba si se quiere una versión especifica de scala como es nuestro caso, si no se instalará la ultima versión (3.8.1)
Una vez instalado almond, podemos comprobar que scala este descargado correctamente para ello volvemos a abrir jupyter lab.
En Jupyter lab, abrimos un cuaderno Scala y comprobamos la versión, yo en mi caso lo he hecho mediante el comando:

- println("Scala " + scala.util.Properties.versionNumberString)

Terminamos realizando los 3 ejercicios simples indicados en la tarea.

## Entorno 2

Para instalar java 17 yo lo haré llendo a https://adoptium.net/es/temurin/releases?version=17 desde el que instalaré el OpenJDK17U-jdk_x64_windows_hotspot_17.0.20.1_1.msi
Ejecutamos el instalador y como lo vamos a usar para varias tareas, yo lo voy a poner como JDK predeterminado.
Comprobamos desde la terminal que el Java 17 se haya instalado bien con where java, java -version y javac -version.

Yo el Visual Studio Code ya lo tenía instalado de antes, unicamente tengo que actualizarlo a la última versión la 1.138

Vamos al apartado de extensiones a la derecha de la pantalla y buscamo Scala (Metals) para instalarla.

Para instalar sbt hay que entrar a la terminal y escribir winget install sbt.sbt, y una vez ha sido instalado podemos comprobar que se ha instalado correctamente con sbt --version.
