# References

## composetest

[Get started with Docker Compose | Docker Documentation](https://docs.docker.com/compose/gettingstarted/)

```
docker-compose up
```

Or ...

```
docker-compose up -d
```

Open `http://localhost:5000/`.

```
docker-compose ps
docker-compose run web env
```

To stop the background container...
```
docker-compose stop
```

To remove the container entirely ...
```
docker-compose down --volumes
```

## composedjango

[Quickstart: Compose and Django | Docker Documentation](https://docs.docker.com/compose/django/)

```
sudo docker-compose run web django-admin startproject composeexample .
```

```
sudo chown -R $USER:$USER .
```

Edit composeexample/settings.py ...

```
# settings.py
   
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'PASSWORD': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}
```

```
docker-compose up
```

```
docker-compose down
```

## composerails

[Quickstart: Compose and Rails | Docker Documentation](https://docs.docker.com/compose/rails/)

```
docker-compose run --no-deps web rails new . --force --database=postgresql
```

```
sudo chown -R $USER:$USER .
```

```
docker-compose build
```

Replace the contents of config/database.yml with the following:

```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password: password
  pool: 5

development:
  <<: *default
  database: myapp_development


test:
  <<: *default
  database: myapp_test
```

```
docker-compose up
```

```
docker-compose run web rake db:create
```

Go to `http://localhost:3000`.

```
docker-compose down
```

To restart ...
```
docker-compose up
```

To rebuild ...
```
docker-compose up --build.
```

```
docker-compose down --volumes
```

## composewordpress

```
docker-compose up -d
```

Go to `http://localhost:8000`.

```
docker-compose down --volumes
```

