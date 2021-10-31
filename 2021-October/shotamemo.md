# GitHubの仕組み

![image](https://user-images.githubusercontent.com/82911032/139564271-b4333a2f-493f-4157-915f-e0b0d2d215cc.png)

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
