# redmine-docker (日本語版)

このプロジェクトは、Docker Compose を使用して Redmine と MySQL を簡単に実行するためのものです。

## 使い方

### 前提条件

*   Docker
*   Docker Compose

### セットアップ

1.  このリポジトリをクローンします:
    ```bash
    git clone https://github.com/yuru-sha/redmine-docker.git
    cd redmine-docker
    ```
2.  `.env.example` ファイルから `.env` ファイルを作成します:
    ```bash
    cp .env.example .env
    ```
3.  `.env` ファイルを編集し、任意のデータベース認証情報を設定します。

### Redmine の実行

コンテナを起動します:
```bash
docker-compose up -d
```

Redmine は http://localhost:3000 でアクセス可能になります。

### Redmine の停止

```bash
docker-compose down
```

### データ削除

データベースとファイルのデータを削除するには、`mysql_data` と `redmine_data` ディレクトリを削除します:
```bash
docker-compose down -v # コンテナを停止し、docker-compose.yml で定義されたボリュームを削除します
rm -rf mysql_data redmine_data
```
**注意:** これにより、すべての Redmine データが完全に削除されます。

## .env 設定

`.env` ファイルは、MySQL データベースの認証情報を設定するために使用されます。`.env.example` をコピーして値を変更してください:

*   `MYSQL_DATABASE`: Redmine が使用する MySQL データベース名。
*   `MYSQL_ROOT_PASSWORD`: MySQL の root ユーザーのパスワード。
*   `MYSQL_USER`: Redmine が MySQL に接続するためのユーザー名。
*   `MYSQL_PASSWORD`: Redmine MySQL ユーザーのパスワード。

## ライセンス

このプロジェクトは MIT ライセンスの下でライセンスされています。詳細は [LICENSE](LICENSE) ファイルを参照してください。(注意: LICENSE ファイルを作成する必要があります)