## Inicio rápido

> Descomprime los recursos o clona el repositorio. Después de obtener el código, abra un terminal y navegue hasta el directorio etapa2G5HDP115, donde esta el código fuente del sistema,

```bash
$ git clone https://github.com/Carlos-Martz/etapa2G5HDP115.git
$ cd etapa2G5HDP115
```

<br />

### Configuración para `Unix`, `MacOS` 

> Instalar módulos mediante `VENV'

```bash
$ virtualenv env
$ source env/bin/activate
$ pip3 install -r requirements.txt
```

<br />

> Configurar la base de datos

```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

<br />

> Iniciar la aplicación

```bash
$ python manage.py runserver
```

En este punto, la aplicación se ejecuta en `http://127.0.0.1:8000/`. 

> Nota: Para acceder al sistema, entra a la página de inicio y autentiquese utilizando las credenciales por defecto ***test / ApS12_ZZs8*** o cree un nuevo usuario con las mismas (o otras) en la **página de registro**. Tras la autenticación, podrá acceder al sistema.

<br />

## Estructura de archivos
Dentro de la descarga encontrará los siguientes directorios y archivos:

```bash
< PROJECT ROOT >
   |
   |-- core/                               # Implementa la configuración de la aplicación
   |    |-- settings.py                    # Define la configuración global
   |    |-- wsgi.py                        # Iniciar la aplicación en producción
   |    |-- urls.py                        # Definir las URL servidas por todas las aplicaciones/nodos
   |
   |-- apps/
   |    |
   |    |-- home/                          # Una aplicación sencilla que sirve archivos HTML
   |    |    |-- views.py                  # Servir páginas HTML para usuarios autenticados
   |    |    |-- urls.py                   # Definir algunas rutas super sencillas  
   |    |
   |    |-- authentication/                # Gestiona las rutas de autenticación (inicio de sesión y registro)
   |    |    |-- urls.py                   # Definir rutas de autenticación  
   |    |    |-- views.py                  # Gestiona el inicio de sesión y el registro  
   |    |    |-- forms.py                  # Definir formularios de autenticación (inicio de sesión y registro) 
   |    |
   |    |-- static/
   |    |    |-- <css, JS, images>         # Archivos CSS, Javascripts
   |    |
   |    |-- templates/                     # Plantillas utilizadas para generar páginas
   |         |-- includes/                 # Trozos y componentes HTML
   |         |    |-- navigation.html      # Componente del menú superior
   |         |    |-- sidebar.html         # Componente de la barra lateral
   |         |    |-- footer.html          # Pie de la aplicación
   |         |    |-- scripts.html         # Scripts comunes a todas las páginas
   |         |
   |         |-- layouts/                   # Páginas maestras
   |         |    |-- base-fullscreen.html  # Utilizado por las páginas de autenticación
   |         |    |-- base.html             # Utilizado por páginas comunes
   |         |
   |         |-- accounts/                  # Páginas de autenticación
   |         |    |-- login.html            # Página de acceso
   |         |    |-- register.html         # Página de registro
   |         |
   |         |-- home/                      # Páginas del kit de interfaz de usuario
   |              |-- index.html            # Página índice
   |              |-- 404-page.html         # Página 404
   |              |-- *.html                # Todas las demás páginas
   |
   |-- requirements.txt                     # Módulos de desarrollo - Almacenamiento SQLite
   |
   |-- .env                                 # Inyectar configuración a través del entorno
   |-- manage.py                            # Iniciar la aplicación - Django script de inicio por defecto
   |
   |-- ************************************************************************
```