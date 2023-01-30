# pet_shelter

## SETUP

#### Clone

Navigate to your python projects directory and clone the repo:

```
git clone https://github.com/daryabelyavskaya/pet_shelter.git
```

#### Local

Open hsf_delivery/ dir as project in your IDE and configure virtual environment, or cd to cloned repo, run venv and
activate it:

```
python3.9 -m venv venv
source venv/bin/activate
```

Install dependencies:

```
pip install -r requirements.txt
```

Before running docker and app, create .env file in the root of project and set the next environment variables:

```
SECRET_KEY="secret_key"
POSTGRES_USER="psql_user"
POSTGRES_PASSWORD="postgres_password"
POSTGRES_DB="postgres_database"
````

#### Docker workflow

Make sure you have **docker** and **docker-compose** installed on your machine, then build and run the app with Compose:

```
docker-compose -f docker-compose.loc.yaml up -d --build
```

You could continue streaming the output from the container’s `STDOUT` and `STDERR` to debug effectively during the
development:

```
docker logs app --follow
```

Stop project-related containers with Compose when your work is done:

```
docker-compose -f docker-compose.loc.yaml stop
```
