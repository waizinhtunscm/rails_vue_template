## 環境

- Docker
- Ruby 2.7.5
- Ruby on Rails 6.1.6
- Mysql 8.0

## 開発環境の構築
```
$ git config --global core.autocrlf false
```
#### Step1 このプロジェクトをCloneする
```bash
$ git clone https://github.com/waizinhtunscm/rails_template.git
```
#### Step2 開発環境ファイルの用意

`.env` `docker-compose.yml` `Gemfile.local` は各自の環境毎に手を加えられるよう、exampleファイルのみGit管理しています。  
以下コマンドを順次実行してください。  

```bash
# 環境変数
$ cp .env.example .env

# docker-compose設定ファイル
$ cp docker-compose.example.yml docker-compose.yml

# 各自の開発環境でのみ必要となるGemfileを記述するGemfile
$ cp Gemfile.local.example Gemfile.local
```
#### Step3 docker-composeを利用した開発環境の起動

以下コマンドを順次実行してください。  

```bash
# DockerfileからDockerイメージ作成
$ docker-compose build

# appコンテナを一時起動しbashでアクセス
$ docker-compose run --rm app bash

# Nodeモジュールのインストール
$ bin/yarn install

# appコンテナへのアクセスを終了
$ exit

# docker-composeサービス群の起動
$ docker-compose up -d
```
あとは `http://localhost:3000` にアクセスすればOKです。 



