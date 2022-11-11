# 概要

- golangを使ったREST APIのサンプル
- 基本的なCRUD操作を行うREST APIです。　
- TODOアプリのバックエンドのイメージでTODO(タイトルと内容)の取得/追加/更新/削除が行えます。


## 参考
> - https://dev.classmethod.jp/articles/go-sample-rest-api/
> - https://github.com/koga456/sample-api


## ディレクトリ構成

- MVCアーキテクチャ風の構成となっている。

```
sample-api/　　ルートディレクトリ
  ┣ build/　　Dockerfileなど
  ┃ ┣ db/ 動作確認用DB
  ┃ ┃  ┣ sql/ DDLとテストデータ投入用SQL
  ┃ ┃ ┗ Dockerfile
  ┃ ┣ sample-api/ 
  ┃ ┃  ┗ Dockerfile このサンプルプロジェクトの実行ファイルを含んだイメージを作成するためのDockerfile
  ┃ ┗ docker-compose.yml
  ┣ cmd/
  ┃  ┗ sample-api
  ┃  ┗ main.go メイン処理
  ┣ controller/
  ┃ ┣ dto/　リクエスト/レスポンス用のDTOファイルを配置する
  ┃ ┣ router.go HTTPメソッドを元にコントローラの各処理へのルーティングを行う
  ┃　　┣ router_test.go `router.go`のテストファイル
  ┃　　┣ todo_controller.go リクエストを元にモデルの各処理を呼び出しレスポンスを返却する
  ┃ ┗ todo_controller_test.go　`todo_controller.go`のテストファイル 
  ┣ model/
  ┃  ┣ entity/　
  ┃  ┗ repository/
  ┣ test/
  　　　　　　　　┗ mock.go 単体テスト用のモック
  ┣ test_results/ 単体テストのカバレッジファイルを配置する            
  ┣ Makefile
  ┣ go.mod
  ┗ go.sum
```

## 起動

```
make serve
```