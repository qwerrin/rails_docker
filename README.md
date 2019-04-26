# Ruby on Rails環境構築


### ■ 前提
ローカル環境にgit,dockerおよびdocker-composeをインストールしていること


※ dockerの構築についてはwindows,mac,linuxによって違うので各自でインストールしてください。



### ■ 使い方
git cloneでリポジトリをローカルに持ってくる。

```
$ mkdir -p ~/rails_docker && cd ~/rails_docker
$ git clone https://github.com/qwerrin/rails_docker.git .

```



### ■ コンテナ起動
dockerコンテナを起動します。

```
$ docker-compose up -d --build
```



### 動作確認
ブラウザで確認。

```
http://localhost:3000
```


### ruby on railsの各種操作

```
# Gemfileを変更した時のりライブラリ更新
$ docker-compose exec rails bundle update
# データベース作成
$ docker-compose exec rails rake db:create
# マイグレーション実行
$ docker-compose exec rails rake db:migrate
# アセットのプリコンパイルを行う
$ docker-compose exec rails rake assets:precompile
```




### コンテナの停止
```
$ docker-compose stop
```



### コンテナの破棄
```
$ docker-compose down -v
```

何か思いついたら更新していきます

