Podman compose で　 rails 環境を構築する
Host は　 macos(intel)
podman desktop を利用します。

podman で作成される db は`postgresql`です

```
podman compose build
```

```
podman compose up -d
```

```
podman compose run web bash

```

```
bin/rails db:create
```

```
exit
```

podman desktop で web のゴミを削除

`localhost:3000`でアクセス
初期画面が表示されると思います。

pgadmin4 でのアクセスは

```
メールアドレス：info@domain.com
パスワード：password
```

となっています。
