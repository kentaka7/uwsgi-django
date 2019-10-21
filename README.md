# uwsgi-django

## 構成

```
uwsgi-django
├── docker-compose.yml
├── mysql
├── sql
├── nginx
│   ├── conf
│   │   └── app_nginx.conf
│   └── uwsgi_params
└── python
    ├── Dockerfile
    └── requirements.txt
```



## Deploy 手順

#### Djangoプロジェクトの実行
```
docker-compose run python django-admin.py startproject app .
```

#### マイグレーションの実施
```
docker-compose run python ./manage.py makemigrations
docker-compose run python ./manage.py migrate
```

#### 管理者の設定
```
docker-compose run python ./manage.py createsuperuser
```

#### コンテナを起動し、ブラウザで確認する
- -dはバックグラウンドで実行を意味する
```
docker-compose up -d
```



### 参考にしたもの
https://qiita.com/kenkono/items/6221ad12670d1ae8b1dd


