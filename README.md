# Swagger generated server

## Overview
This server was generated by the [swagger-codegen](https://github.com/swagger-api/swagger-codegen) project. By using the
[OpenAPI-Spec](https://github.com/swagger-api/swagger-core/wiki) from a remote server, you can easily generate a server stub.  This
is an example of building a swagger-enabled Flask server.

This example uses the [Connexion](https://github.com/zalando/connexion) library on top of Flask.

## Environment Setup
 * Install [Git](https://git-scm.com/downloads) to clone the project via repo URL or download the .zip from the website:
    * `git clone https://github.com/VertexChat/norton`
 * Install [Python 3.7](https://www.python.org/downloads/)
 * [Install](https://virtualenv.pypa.io/en/latest/installation/) & set up a [python virtual environment](https://docs.python.org/3/tutorial/venv.html#creating-virtual-environments) 
 inside the project directory:
    * Install with `pip3 install virtualenv` or through your package manager on linux | Windows `pip install virtualenv`
    * `cd /norton`
    * `python3 -m venv ./venv` | Windows `python -m venv ./venv`
        * this will create a virtual environment called venv, you may name it what you like.
 * To activate virtual environment created inside the project directory:
    * Linux: `source venv/bin/activate` | Windows `.\venv\Script\activate`

 * Install the [required python packages](https://docs.python.org/3/tutorial/venv.html#managing-packages-with-pip) listed in the [requirements.txt](https://github.com/butlawr/Emerging-Technologies-Project/blob/master/requirements.txt) file, this can be done by:
    * Note: Regardless of which version of Python you are using, when the virtual environment is activated, you should 
    use the pip command not `pip3`
    * `pip install -r requirements.txt`

## MySQL Config
This server when starting needs to connect to a MySQL database, to do so make a `config.ini` 
and populate it with where blank you need to fill in your information

```
[client]
user=
password=
host=
port=3306
database=vertex_db
```

## Usage
To run the server, please execute the following from the root directory:

```
pip3 install -r requirements.txt
python3 -m swagger_server
```

and open your browser to here:

```
http://localhost:8080/ui/
```

Your Swagger definition lives here

```
http://localhost:8080/swagger.json
```

To launch the integration tests, use tox:
```
sudo pip install tox
tox
```

## Running with Docker

To run the server on a Docker container, please execute the following from the root directory:

```bash
# building the image
docker build -t swagger_server .

# starting up a container
docker run -p 8080:8080 swagger_server
```