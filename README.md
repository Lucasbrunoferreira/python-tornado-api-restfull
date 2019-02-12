# Tornado API RESTful - Python

## English

This is a simple example, to implements a http web server (API RESTfull) with python (tornado framework).


### Dependencies

| Dependency        | For what?           | Link  |
| ------------- |:-------------:| -----:|
| tornado | web framework server    |    https://www.tornadoweb.org/ |
| pymongo      | mongo database driver | https://api.mongodb.com/python/current/ |
| marshmallow      | fileds schema validator     |   https://marshmallow.readthedocs.io |
| logzero | create application logs   |    https://logzero.readthedocs.io/en/latest/ |
| unittest | unit tests   |    https://docs.python.org/3/library/unittest.html |


### Routes

* GET - `/api/v1/users` - Get all users
* GET - `/api/v1/users/{user_id}` - Get only the user for the id entered in the parameter
* POST - `/api/v1/user` - Create new user
* PUT - `/api/v1/users/{user_id}` - Edit the user referring to the id entered in the parameter
* DELETE - `/api/v1/users/{user_id}` - Delete the user referring to the id entered in the parameter

### Architecture

* **Handlers** - It is the layer responsible for manipulating requests and performing business rules.

* **Persistence** - Layer responsible for data manipulation.

    * **Schemas** - Data modeling.
    
    * **Database** - Connection and manipulation with database.
    
* **Tests** - Layer with unit application tests

* **Util** - Gathers higher-use (repetitive) codes in the project.


### Tests
Run all unit application tests
* `cd project-folder`
* `python -m unittest`

### Run
After preparing your environment and your virtualenv, follow the steps:

* `cd project-folder`
* `pip install -r requirements.txt`
*  set the MONGO_URI environment variable (for connection to the database) and the APP_PORT variable (port on which the application will run) on your machine, or manually change the settings.py file.
* `python main.py`

Run application with docker:
* `cd project-folder`
* `docker build -t api-tornado-img .`
*  set a MONGODB_URI environment variable no following command and run it.
* `docker run -d -p 8080:8080 --name api-tornado -e MONGO_URI="mongodb://user:password@host:port/database" api-tornado-img:latest`
* your application is running in 8080 port

##


## Português - Brasil

Este é um exemplo simples, para implementar um servidor web http (API RESTfull) com python (framework tornado).


### Dependências

| Dependência        | Qual o uso?           | Link  |
| ------------- |:-------------:| -----:|
| tornado | servidor web    |    https://www.tornadoweb.org/ |
| pymongo      | conexão com o banco de dado NoSQL mongo | https://api.mongodb.com/python/current/ |
| marshmallow      | validação de campos e dados     |   https://marshmallow.readthedocs.io |
| logzero | criação de logs da applicação   |    https://logzero.readthedocs.io/en/latest/ |
| unittest | testes unitários   |    https://docs.python.org/3/library/unittest.html |

### Rotas

* GET - `/api/v1/users` - Buscar todos os usuários cadastrados
* GET - `/api/v1/users/{user_id}` - Busque apenas o usuário referente ao id informado no paramêtro
* POST - `/api/v1/users` - Criar um novo usuário
* PUT - `/api/v1/users/{user_id}` - Editar o usuário referente ao id informado no parâmetro
* DELETE - `/api/v1/users/{user_id}` - Deletar o usuário referente ao id informado no parâmetro

### Arquitetura

* **Handlers** - É a camada responsável por manipular as requisições e realizar as regras de negócios.

* **Persistence** - Camada responsável pela manipulação de dados.

    * **Schemas** - Modelagem de dados.
    
    * **Database** - Conexão e manipulação com banco de dados.

* **Tests** - Camada com os testes unitarios da aplicação

* **Util** - Reúne códigos de uso mais alto (repetitivos) no projeto


### Executar os Testes
Para realizar todos os testes do projeto, execute:
* `cd project-folder`
* `python -m unittest`


### Executar a aplicação

Depois de preparar seu ambiente e seu virtualenv, siga os passos:

* `cd project-folder`
* `pip install -r requirements.txt`
*  defina a variavél de ambiente MONGO_URI (para conexão com o  banco) e a variavél APP_PORT (porta na qual a aplicação sera executada) em sua maquina, ou altere manualmente no arquivo settings.py.
* `python main.py`

Se preferir, pode executar a aplicação com o docker:
* `cd project-folder`
* `docker build -t api-tornado .`
* defina a variavél de ambiente MONGO_URI no comando aseguir e execute-o.
* `docker run -d -p 8080:8080 --name api-tornado -e MONGO_URI="mongodb://user:password@host:port/database" api-tornado-img:latest`
* sua aplicação esta rodando na porta 8080
