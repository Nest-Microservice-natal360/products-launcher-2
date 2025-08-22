

## 開発

1. リポジトリをクローンする
2. `env.template` に基づいて `.env` ファイルを作成する 
3. `git submodule update --init --recursive` の実行
4. `docker compose up --build` の実行



### Git サブモジュールの作成手順

1. GitHub に新しいリポジトリを作成します。
2. リポジトリをローカルマシンにクローンします。
3. サブモジュールを追加します。`repository_url` はリポジトリの URL、`directory_name` はサブモジュールを保存するフォルダの名前です（プロジェクト内に存在しない必要があります）。
```
git submodule add <repository_url> <directory_name>
```
4. リポジトリに変更を追加します (git add、git commit、git push)。
例:
```
git add .
git commit -m "Add submodule"
git push
```
5. サブモジュールを初期化して更新します。リポジトリを初めてクローンする際は、サブモジュールを初期化して更新するために、以下のコマンドを実行する必要があります。
```
git submodule update --init --recursive
```
6. サブモジュールの参照を更新するには
```
git submodule update --remote
```

## 重要
サブモジュールを含むリポジトリで作業している場合は、**まずサブモジュールを更新してプッシュ**し、**次に**サブモジュールをメインリポジトリにプッシュしてください。

これを逆に行うと、メインリポジトリのサブモジュール参照が失われ、競合を解決する必要があります。