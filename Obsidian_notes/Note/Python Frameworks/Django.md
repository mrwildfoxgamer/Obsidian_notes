`It is a python web frame work used to devolop dynamic and database-driven web applications`

project_name/
>--manange.py
>project_name/
>	__ init __ .py
>	admin.py
>	urls.py
>	asgi.py
>	wsgi.py
>myapp/
>	__ init __ .py
>	admin.py
>	app.py
>	models.py
>	views.py
>	tests.py
>	urls.py

#### manange.py
_A command_line utility used to manage Django projects_
*used to run the deployment server. Create applications, perform migrations etc*


#### Settings.py
*contains the configurations settings of the project*
- Database configuration
- installed application
- security settings
- templates
#### Urls.py
*defines the URL routing of the application*

#### Views.py
*Contains the business logic of the application*

#### Models.py
Defines the database structure using python classes 

#### Templates 
Templates are usually HTML files used to create the user interface*

#### Admin.py
used to register models with Django/s built in administration interface

#### wsgi.py and asgi.py
*There files help Django communicatie with web servers and are mainly used when deplying a django application*
