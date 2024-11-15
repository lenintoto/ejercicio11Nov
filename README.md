Para comenzar nos dirigimos a Firebase donde vamos a poder crear una aplicación Ionic con autenticación y carga de archivos. Para esto nos digimos al proyecto que se creo y tenemos que habilitar la base de datos, 
así que seleccione Base de datos de Firestore en el menú y haga clic en Crear base de datos .

![image](https://github.com/user-attachments/assets/b39a83cd-e68e-4fb8-a76e-1302e81883d3)

Tambien como Como queremos trabajar con usuarios, también debemos ir a la pestaña de Autenticación , hacer clic en Comenzar nuevamente y activar el proveedor de correo electrónico y contraseña . 
Esto nos permite crear usuarios con una combinación estándar de correo electrónico y contraseña.

![image](https://github.com/user-attachments/assets/daea8a6b-a1d5-4519-a5dc-db92a1abb25a)

El último paso es habilitar el Almacenamiento pero en este caso como esto requiere un plan se utilizo las credenciales del Ing. Juan Pablo Zaldumbide para allí guardar las imagenes.

Para la aplicacion necesitamos es una plantilla en blanco, una página adicional y dos servicios para la lógica de nuestra aplicación

Ejecutamos los siguientes comandos:

ionic start "Nombre de la app" blank --type=angular
ionic g page login
ionic g service services/auth
ionic g service services/avatar

npm i @capacitor/camera
npm i @ionic/pwa-elements

ng add @angular/fire

Para utilizar esos elementos PWA, abrimos src/main.ts e importamos y llamamos a la defineCustomElementsfunción
Nos dirigimos a environment/environment.ts donde colocaremos las credenciales correspondientes.

![image](https://github.com/user-attachments/assets/1abc2bb8-448d-4ee8-a82a-2b4a6bc9cec4)

# Construyendo la lógica de autenticación
Toda la lógica estará en un servicio separado y necesitamos solo tres funciones que simplemente llamen a la función de Firebase correspondiente para crear un nuevo
usuario, iniciar sesión como usuario o finalizar la sesión actual.
Para esto de modifica los siguientes archivos: 
- src/app/services/auth.service.ts
- src/app/login/login.module.ts
- src/app/login/login.page.ts
- src/app/login/login.page.html
Con esto ya todo estaria la pagina principal y ya se guarda los usuarios.

![image](https://github.com/user-attachments/assets/5ea56f66-02ec-4a53-aafd-073adb51e3bf)

![image](https://github.com/user-attachments/assets/224a9a79-f491-4aa4-b0d2-8b4596e36409)

#   Subir archivos de imagen a Firebase

Al igual que antes, ahora comenzaremos con la implementación del servicio. El servicio debe devolver en primer lugar el documento de un usuario en el que planeamos almacenar la 
referencia/enlace del archivo al avatar del usuario.
Para esto se modifican los siguientes archivos.
- src/app/services/avatar.service.ts
- src/app/home/home.page.ts
- src/app/home/home.page.html
- src/app/home/home.page.scss

y con esto ya estaria todo la carga de imagenes pero en este caso se ve representado en el Firebase del Ing. Juan Pablo Zaldumbide ya que el almacenamiento es con un plan el cual nosotros los estudiantes no contamos.
Pero la pantalla con el avatar quedaria de la siguiente manera ademas de la carpeta en donde se guardaran las imagenes que en este caso son los apellidos de los estudiantes que crearon la app.

![image](https://github.com/user-attachments/assets/2394b853-104a-4612-9f74-9144b4d659c1)
![image](https://github.com/user-attachments/assets/5d24927d-28f5-4012-a94f-212c2ec8aecc)

