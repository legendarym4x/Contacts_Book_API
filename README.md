### Contacts Book REST Api (Final project)

In this work, we created a REST API application to manage the contact book for users. The API is built using the 
FastAPI framework and SQLAlchemy for database management.

Contacts are stored in the database and contain the following information:

     Name
     Surname
     E-mail address
     Phone number
     Birthday
     Date of creation

The API has the ability to perform the following actions:
    
     Create a new contact
     Get a list of all contacts
     Get one contact per ID
     Update an existing contact
     Delete contact

In addition to the basic CRUD functionality, the API also has the following features:

     Contacts are available for search by name, surname or e-mail address (Query).
     The API should be able to retrieve a list of contacts with birthdays for the next 7 (or whatever) days.


General requirements:

     Using the FastAPI framework to create APIs.
     Using ORM SQLAlchemy to work with the database.
     PostgreSQL was used as a database.
     Support for CRUD operations for contacts.
     Support for storing a contact's date of birth.
     Provide API documentation.
     Using the Pydantic data validation module.
     Implement the authentication mechanism in the application.
     Implement an authorization mechanism using JWT tokens so that all operations with contacts are performed only 
     by registered users.
     The user has access only to his transactions with contacts.
     Implement a mechanism for verifying the registered user's e-mail.
     Enable CORS for your REST API.
     Implement the ability to update the user's avatar. Use the Cloudinary service.
     All environment variables must be stored in an .env file. There should be no confidential data in the "clean" form
     inside the code.
     Docker Compose is used to run all services and databases in the application.
     Using Sphinx, we created the documentation for our project. To do this, docsrings were added to the necessary 
     functions and class methods in the main modules.
     Covered the repository modules of our project with unit tests using Unittest framework.
     We covered the authentication route from our project with functional tests using Pytest framework.

The authentication process, as well as updates, are performed in the Postman program, which is very convenient for 
this purpose.

To run the application, you must first start a Docker Compose containers (`docker compose up -d`) with postgres, Redis
and install the poetry virtual environment along with the necessary libraries.

Then you need to execute the following commands:

    - to create migrations:

        * alembic init migrations
        * alembic revision --autogenerate -m "Init"
        * alembic upgrade head

    - to launch the application:

        * uvicorn main:app --host localhost --port 8000 --reload

    - to run the pytest tests:

        * python -m pytest tests/ 