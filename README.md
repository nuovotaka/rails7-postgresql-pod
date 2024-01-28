```
podman compose run web rails new . --force --skip-bundle

```

一旦、control + c でストップし

```
podman compose run web bash
bundle install
```

db のユーザー名とパスワードを指定する

```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
+  username: ps
+  password: password
...
production:
  <<: *default
  database: myapp_production
-  username: myapp
-  password: <%= ENV["MYAPP_DATABASE_PASSWORD"] %>

```

```
podman compose up
```

`localhost:3000`にブラウザでアクセス

```
podman compose run web bash
bundle install
bin/rails db:create
```

```
podman compose up
```

`localhost:3000`にブラウザでアクセス
