# PostgreSQL 導入資料

## PostgreSQL 13 のインストール

### Windowsユーザ向け

1. [PostgreSQLのダウンロード](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)を開く
2. `PostgreSQL Version 13.x` 行の`Windows x86-64`列の`Download`リンクをクリックする
3. ダウンロードしたインストーラを起動する
  1. `Installation Directory`はデフォルトのまま
  2. `Select Components`のチェックはデフォルトのまま
  3. `Data Directory`はデフォルトのまま
  4. **注意!** 忘れると取り返しがつかないため、ユーザーpostgresのパスワードは`postgres`とすること
  5. `Port`はデフォルトのまま(5432)
  6. `Advanced Options`の`Locale`は`Japanese, Japan`とすること
  7. `Ready to Install`まで`next`を押してPostgreSQLをインストールする
  8. `Completing the PostgreSQL Setup Wizard`と表示されたら、`Launch Stack Builder at exit?`のチェックを外して`Finish`を押して完了

最後に、[このサイト](https://www.javadrive.jp/postgresql/install/index3.html)を参考にパスを通してください。  
デフォルトのままだとインストール先は`C:\Program Files\PostgreSQL\13\bin`になるかと思いますので、サイト内で  

> (ご自身が PostgreSQL をインストールしたディレクトリに合わせて入力して下さい)

とされているところにこれを設定します。

### Macユーザ向け

ターミナルにて、`brew install postgresql@13` と入力し実行する  

インストールした際に以下のような指示があればこれに従う（パスを通す）
```
If you need to have postgresql@13 first in your PATH, run:
  echo 'export PATH="「homebrewのインストール先」/postgresql@13/bin:$PATH"' >> ~/.zshrc
```

`「homebrewのインストール先」`は環境によって異なるかもしれません。`brew info postgresql@13`で確認できるはずです。

※もし、homebrewがうまくいかないときは、homebrew自体をなんとかするか、[PostgreSQLのダウンロード](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)を開いてMac版のインストーラをダウンロードしてください。以降の手順はWindowsのほうを参考に進められると思います。（未検証）

issue [#1](https://github.com/TakashiNishimura/PostgreSQL-intro/issues/1) のような情報もいただきました。こちらもご参考ください。

## インストールの確認

コンソール（ターミナル）にて、`psql --version`を実行してバージョンが表示されればインストール済み  

※Windowsだと、パスを通したあとに新しく開いたコンソールじゃないとコマンドたたけないです。
