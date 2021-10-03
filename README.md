# Simply-Menu
Ensure you have Python 3.9 and Docker installed.

## Setup virtual environment
A virtual environment will allow you to separate dependencies and versions in this python project from your global python installation.

From the root of this project:
- Install virtualenv: `pip3 install virtualenv`
- Create a new virtual environment "venv": `virtualenv venv`
- Activate the environment: `source venv/bin/activate`

To exit the virtual environment, simply type `deactivate`

## Setup dev environment
Whilst in your virtual environment:
- `pip3 install -r requirements.txt`
- `cp .env.example .env`
- `python -c "import secrets; print(secrets.token_urlsafe())"`
- Copy the string from the previous command and add it to the `SECRET` key in the `.env` file

## Setup database
- Run Docker
- Set `DB_PASSWORD` in your `.env` file
- Initialise the database container: `docker-compose up`
- Run migrations: `./manage.py migrate`

## Tests
To run the test suite:
- `./manage.py test`

