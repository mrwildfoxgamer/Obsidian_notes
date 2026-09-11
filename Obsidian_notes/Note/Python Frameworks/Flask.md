*IT is a  lightweight open source web framework for python it is intended to be simple and flexible*

features include :
1. Receiving HTTP requests 
2. figuring out which URL was requested 
3. Generating HTTP responses
4. Handling routing
5. dealing with cookies and headers
6. generating HTML

>Flask provides the basic functionality needed to build web applications without imposing a large framework structure
>
>Flask Include built in development server so that no need for 3rd party software to test your application during development
>
>Routing connects URLs to Python function
```
@app.route('/about')
def about():
    return "About Page"
```
`when visising /about`  `about() gets exicuted`

#### Template Engine

*flask uses jinja it allows you to generate HTML dynamically*
```
<h1>Hello {{ username }}</h1>
```

#### Extensible
Flask can be extended through additional packages/extentions
These provide functionality that flask's core doesn't  have

#### REST API friendly
Flask is commonly used for APIs


```
pip install flask is used to install flask pip is the package manager
it is recomented to do it in a virtual environment to avoid conflicts 
```

### The basic Flask application
```
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello, World!"

if __name__ == '__main__':
    app.run(debug=True)
```


> @app.route() is a **decorator**.
`A decorator modifies or registers a function.`

`python app.py` to run a flask application

### Converters 
| Converter | Meaning                     | Example                 |
| --------- | --------------------------- | ----------------------- |
| `string`  | Text without `/`            | `/post/<string:title>`  |
| `int`     | Integer                     | `/post/<int:post_id>`   |
| `float`   | Floating-point number       | `/price/<float:amount>` |
| `path`    | String that may contain `/` | `/files/<path:subpath>` |
| `uuid`    | UUID value                  | `/session/<uuid:id>`    |
### HTTP methods
Common http methods are 
```
GET-sends a GET request.
POST -used to send data to the server.
PUT-Update/replace data
DELETE-Delete data
```
>Flask routes respond to **GET by default**

```
                     Flask Application
                            │
                            ▼
                     HTTP Request
                            │
                            ▼
                     URL Routing
                            │
             ┌──────────────┴──────────────┐
             │                             │
       Static route                 Dynamic route
       /about                      /user/<name>
             │                             │
             ▼                             ▼
        Python function             Python function
             │                             │
             └──────────────┬──────────────┘
                            ▼
                        Response
                            │
                            ▼
                         Browser
```

```
Browser/Form
    │
    ▼
POST /login
    │
    ▼
Flask route
    │
    ▼
request.method == "POST"
    │
    ▼
Process data
    │
    ▼
Response
```


### Werkzeug and Jinja
## Werkzeug

Werkzeug is a **WSGI toolkit** used by Flask for things such as:

- request handling
- response handling
- routing
- HTTP utilities
- development server functionality
- debugging
## Jinja

Jinja is the **template engine**.

It lets you combine HTML with dynamic data.
`<h1>Hello {{ name }}</h1>`


### Request handling.
When you use a Flask application, the browser and server communicate through **HTTP requests and responses**.

```
Browser
   ↓
HTTP Request
   ↓
Flask
   ↓
Python code
   ↓
HTTP Response
   ↓
Browser
```

>Request object it is a global object containing the incoming data send by the browser
>
>`request.args` let you access query parameters

### Request cycle

1. The browser send an HTTP request
2. Flask can run special code before the actual route function executes
	- `before_request` is for work that should happen before the view function.
3. Route matching and view execution after prepossessing flak determines which route matches the request URL
4. after the view function finishes flask can run another type of function `After_request`
	- this can be used for things such as saving database changes or modifying response headers
5. Response is send Finally flask sends a response back to the client 



# Query Parameters

A **query parameter** is additional information attached to a URL after a `?`.
They are represented as **key-value pairs**. 
`URL path + query parameters`
Query parameters are useful when information needs to be supplied through the URL, especially for things such as searching, filtering, pagination, and optional settings.

`Multiple parameters are separated using `&`.

`?key=value&key=value`

#### Request.args
`request.args` is used to access **query parameters** from the URL.

The important idea is that the URL isn't only used to identify a resource.
It can also carry **additional input from the client**.
Flask exposes this information through `request.args`.
#### request.args.get()
The purpose of `get()` is to retrieve a parameter while allowing a **default value** when that parameter is missing.

**`get(parameter)` → retrieve the parameter**
`get(parameter, default=value)` → retrieve it, or use the fallback value if it doesn't exist

# Default Values

A **default value** is the value Flask uses when a requested query parameter is not supplied.**Parameter exists → use supplied value**
**Parameter missing → use default value**
