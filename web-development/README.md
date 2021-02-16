# Dockerfiles

## web-development

### Djangoプロジェクト作成
```
docker-compose run --rm web django-admin.py startproject {project-name} .
```
### データベース設定
```
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
### 起動
```
docker-compose up -d (--build)
```
### アプリ作成
```
docker-compose run --rm web django-admin startapp app
```
### その他
```
makemigrations:
   docker-compose run --rm web python3 manage.py makemigrations

migrate:
   docker-compose run --rm web python3 manage.py migrate

createsuperuser:
   docker-compose run --rm web python3 manage.py createsuperuser
```