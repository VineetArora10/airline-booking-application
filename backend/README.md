This is a base node.js project template, which anyone can use as it has been prepared, by keeping some of the most important code principles and project management recommendations. Feel free to change anything.

`src` -> Inside the src folder, all the actual source code regarding the project will reside. This will not include any kind of tests. (You might want to make separate tests folder).

Lets take a look inside the `src` folder

- `config` -> In this folder, anything and everything regarding any configurations or setup of a library or modules will be done. For example: setting up `dotenv` so that we can use the environment variables anywhere in a cleaner fashion, this is done in the `server-config.js` file. One more example can be to setup the logging library that can help you to prepare meaningfull logs, so configuration for this library should also be done here.

- `routes` -> In the routes folder, we register a route and the corresponding middleware and controllers to it. 

- `middlewares` -> They are just going to intercept the incoming requests where we can write our validators, authenticators, etc.

- `controllers` -> They are kind of the last middlewares as post them you call your business layer to execute the business logic. In controllers we just recieve the incoming requests and data, and then pass it to the business layer, and once business layer returns an output, we structure the API response in controllers and sends the output.

- `repositories` -> This folder contains all the logic using which we interact the database by writing queries, all the raw queries or ORM queries will go here.

- `services` -> This folder contains the business logic and interacts with repositories for data from the database.

- `utils` -> This folder contains the helper methods, error classes, etc.

### Setup the project

- Download this project from github and open it in your favourite code editor.
- In the root directory create a `.env` file and add the following env variables
    ```
        PORT=<port number of your choice>
    ```
    ex:
    ```
        PORT=3000
    ```
- Inside the `src/config` folder create a file named as `config.json` and write the following code:
    ```
        {
            "development": {
                "username": "root",
                "password": null,
                "database": "database_development",
                "host": "127.0.0.1",
                "dialect": "mysql"
            },
            "test": {
                "username": "root",
                "password": null,
                "database": "database_test",
                "host": "127.0.0.1",
                "dialect": "mysql"
            },
            "production": {
                "username": "root",
                "password": null,
                "database": "database_production",
                "host": "127.0.0.1",
                "dialect": "mysql"
            }       
        }
    ```
- If you are setting up your development environment, then write the username of your database, password of your database, and in dialect, mention whatever database you are using for example: mariadb, mysql, etc.
- If you are setting up test or production environment, make sure you also replace the host with the hosted database url.