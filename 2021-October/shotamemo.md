# GitHubの仕組み

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f4474179-3d6a-4980-94ff-b78ba6b25d53/Untitled.png)

`Repository`

ファイルやディレクトリの保管場所

`Index/Stage`

変更後ファイルの一時的な保管場所

`Working Tree`

実際に作業するディレクトリ

Macではターミナル、Windowsではコマンドプロンプトで動かします。

# コマンドプロンプトで動かすコマンド

## Gitのバージョン確認

以下のコマンドを入力すれば、Gitのバージョンをインストールできる。

```powershell
git --version
git version 2.31.1.windows.1
```

## ローカルリポジトリの作成

```powershell
git init
```

## ファイルの登録

```powershell
git add <ファイル名> <ファイル名> .... // ファイル名を指定して登録する場合
git add . // すべてのファイルを登録
```

## リモートリポジトリの登録

```powershell
git remote add origin <リモートリポジトリのURL>
```

## ローカルリポジトリからリモートリポジトリへの送信

```powershell
git push origin <送信先Repository>
git push origin main
```

これでGitで指定したファイルをGitHubにアップロードできる。
