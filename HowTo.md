Antes de comenzar a utilizar esta caracteristica de Node-Red debemos hacer varias cosas.

En primer lugar debemos tener instalado Node-Red en nuestra computadora.

Para mas informacion se puede ver el siguiente link:

https://nodered.org/docs/getting-started/windows

Luego tenemos que tener instalado tambien Git:

https://git-scm.com/downloads

Una vez instalado podemos ver que haciendo click derecho en el escritorio tenemos en el menu contextual la opción de lanzar Git Bash desde ahi:

![Captura 1](https://github.com/ispezia/How-To-Nodered-Projects/blob/master/Imagenes/Anotaci%C3%B3n%202020-06-02%20205830.jpg)

Lanzamos una terminal para configurar nuestro usuario y correo electronico (en el entorno global):
```
git config --global user.name "usuario"
git config --global user.email "correo@dominio.com"
```
Para comprobar de que quedó configurado:
```
git config -–global –list
```
> _Nota: En WIN10 el archivo de configuracion (.gitconfig) por defecto se ubica en "C:\Users\xxxxxxx\"_

Lo ultimo que tenemos que hacer es crear una llave de autenticacion SSH. Nos dirigimos a la carpeta raíz de nuestro usuario, creamos una carpeta llamada .ssh. Lanzamos otra terminal de Git Bashh desde alli y mediante el comando shh-keygen creamos una clave asociada a la cuenta de correo. Vamos a emplear una clave tipo RSA, de modo que el comando quedaría:
```
ssh-keygen -t rsa -C “correo@dominio.com”
```
Nos pregunta que dónde queremos guardar el fichero con la clave y dejamos la opción predefinida.
Podemos corroborar dentro de la carpeta .ssh que se han creado dos archivos, el archivo .pub es la clave pública, que enviaremos a GitHub. Para ello debemos abrir el documento con el bloc de notas y copiar su contenido.

Iniciamos sesión en GitHub y vamos a Settings>>>SSH and GPG Keys y creamos una nueva Key, esta clave pubica quedará asociada al equipo desde el que trabajamos.

Por ultimo desde la terminal debemos ejecutar este comando para autenticarnos:
```
ssh -T git@github.com
```
Si todo está bien nos devuelve un mensaje connuestro usuario y nos avisa que la autenticacion se realizó correctamente.

Hasta acá esos son todos los pasos previos necesarios para trabajar con los proyectos en Node-red y poder tenerlos en repositorios de GitHub.
Dentro de Node-Red vamos a los "User Settings" desde el menu y nos posicionamos en la pestaña "Git Config":

![Captura 2](https://github.com/ispezia/How-To-Nodered-Projects/blob/master/Imagenes/Anotaci%C3%B3n%202020-06-01%20222124.jpg)

Vamos a dejar el usuario y el email en blanco para que tome los de la configuracion global que seteamos anteriormente y en la SSH Keys podemos ver que ya detectó la que creamos en el paso anterior.

Lo siguiente es linkear en los ajustes del proyecto el repositorio remoto que previamente debimos crear en GitHub con nuestro proyecto:

![Captura 3](https://github.com/ispezia/How-To-Nodered-Projects/blob/master/Imagenes/Anotaci%C3%B3n%202020-06-01%20222207.jpg)

Una vez hecho esto ya estamos en condiciones de hacer nuestros primeros commits y push desde la interfaz de Node-Red

![Captura 4](https://github.com/ispezia/How-To-Nodered-Projects/blob/master/Imagenes/Anotaci%C3%B3n%202020-06-02%20214634.jpg)
 
Para ver en detalle como es la operacion de esto ultimo les recomiendo este video:

https://www.youtube.com/watch?v=Bto2rz7bY3g







