### My Django Docker Boilerplate for dev & production

## Development
Using docker for development

````
git clone git@github.com

cp .env.dev.example .env.dev
cp .env.db.dev.example .env.db.dev

# Change .env.* to your configuration setup

$ docker-compose up -d --build

# check
$ docker-compose logs -f

# run migration
$ docker-compose exec web python manage.py makemigration
$ docker-compose exec web python manage.py migrate --fake-initial
$ docker-compose exec web python createsuperuser
````

## Production
````
$ docker-compose -f docker-compose.production.yml up -d --build
$ docker-compose -f docker-compose exec web python manage.py makemigration
$ docker-compose -f docker-compose exec web python manage.py migrate --fake-initial
````