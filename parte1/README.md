Para instalar Jupyter podermos encontrar información en la web: https://jupyter.org/install
Como esta indica ejecutamos el comando "pip install jupyterlab" en nuestro cmd, que comprobará si tenemos todo lo requerido para jupiter y los instalará si no los tenemos.
Una vez instalado jupyter, hay que usar el comando "jupyter lab" en nuestro cmd, el cual abrirá http://localhost:8888/lab en nuestro navegador, desde donde podremos trabajar con jupyter
Para instalar almond, entraremos en https://almond.sh/ y haremos click en la opción de install, eso nos llevará a https://almond.sh/docs/quick-start-install.
Te indica que debes tener instalado Java 1.8.0_121, yo ya lo tengo instalado pero en caso de no tenerlo, te proveé del enlace para descargarlo.
Antes de instalar almond debes de instalar coursier, en la página web indica que hay que usar los comandos:
> bitsadmin /transfer downloadCoursierCli https://git.io/coursier-cli "%cd%\coursier"
> bitsadmin /transfer downloadCoursierBat https://git.io/coursier-bat "%cd%\coursier.bat"
A mi no me han funcionado, y con ayuda de la IA, se que es por que no son comandos actualizados, en su lugar yo usaré:
curl -fLo cs-x86_64-pc-win32.zip https://github.com/coursier/launchers/raw/master/cs-x86_64-pc-win32.zip
Extraigo el zip en la carpeta donde lo he descargado.
Aunque no sea obligatorio por consejo de la IA, voy a renombrar lo extraido (cs-x86_64-pc-win32.exe) a cs.exe para mayor comodidad a la hora de ejecutar comandos con:
move cs-x86_64-pc-win32.exe cs.exe
Ahora que ya tengo correctamente instalado coursier, puedo instalar almond con .\cs launch --use-bootstrap almond -M almond.ScalaKernel -- --install
