This guide shows you how to access debug tools and your local database, despite both the app and database being run through Docker.

Adapted from the following Jetbrains resources:
- [Using Docker Compose as a remote interpreter](https://www.jetbrains.com/help/pycharm/using-docker-compose-as-a-remote-interpreter.html#docker-compose-remote)
- [Connect to Postgres database](https://www.jetbrains.com/help/pycharm/relational-databases.html#connect-to-postgresql-database)

## Setup Remote Interpreter

Open the `Add Python Interpreter` dialog in one of two ways:
- When you're in the `Editor`, the most convenient way is to use the `Python Interpreter` widget in the bottom right.
Click the widget and select `Add Interpreter ...`
- If you are in the `Settings/Preferences` dialog `Ctrl+Alt+S`, select `Project <project name> | Python Interpreter`.
Click the three dots icon and select `Add`.

In the dialog that opens, select the `Docker Compose` option and fill out the form as follows:
    
    Docker Server: Docker
    Configuration file(s): ./docker-compose.yml (or other path to the project's docker-compose.yml file)
    Docker Service: app
    Environment variables: 
    Python interpretor path: python
    
Next, wait while PyCharm starts your Docker-Compose configuration to scan and index:


## Docker-Compose Run Configuration

Create an ordinary `Django Server` run/debug configuration.
To do that, from the main menu choose `Run | Edit Configurations...`;
in the dialog that opens click the `+` icon and select `Django Server`:

Ensure that these fields are set properly:

    Name: RunDjangoApp
    Host: 0.0.0.0
    Port: 8000
    Python interpreter: Remote Python ... (the same as the remote interpreter from the previous step)

*NOTE: Setting the host to 0.0.0.0 is so that Docker can listen to requests from outside itself.
The website will still be at localhost:8000 when launched*

Optionally, set:

    Run browser: http://localhost:8000
    
Launch this configuration with `Run | Run 'RunDjangoApp'`.

To see output in your web browser, go to http://localhost:8000.


## Connecting to the Database

1. In the Database tool window (`View | Tool Windows | Database`), click the `Data Source Properties` icon .
1. On the `Data Sources` tab in the `Data Sources and Drivers` dialog, click the `+` icon and select `PostgreSQL`.
1. Fill in the following information:
    
        Host: localhost
        Port: 25432
        Authentication: User & Password
        User: (same as DB_USER in docker_compose.yml)
        Password: (same as DB_PASSWORD in docker_compose.yml)
        Database: (same as DB_DATABASE in docker_compose.yml)

    *NOTE: If given the prompt to test your connection, do so to be sure your details are correct.*

Now your `Database` window in PyCharm will allow you to access the project's DB without the need of external tools like pgadmin.