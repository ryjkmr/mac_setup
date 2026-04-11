# セットアップ手順

## 1. 新Macを起動、AppleIDでログイン
キーチェーンなどが同期

## 2. 移行ツールで個人設定のみを移行
メールアカウントなどを移行

## 3. git（CLT）を有効化
インストールする基本アプリケーションのリストはgithubにあるので、git cloneするためのgitを有効化する
```
git --version
```
→ Xcode CLIのインストールを促すダイアログが出るのでインストール

## 4. このリポジトリをローカルにクローン
```
git@github.com:ryjkmr/mac_setup.git
```

## 5. Homebrewをインストール
基本アプリケーションはHomebrewで入れる
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
## 6. cloneしたBrewfileを元に基本アプリを自動インストール
```
brew bundle
```

## 7. Dropboxと1Passwordにログインして有効化
- Dropboxはパスキーでログイン
- 1PasswordはID、パスワード、SECRET-KEYが必要

## 8.Dropbox上のsetup-local.shを実行
```
./setup-local.sh
```

## 9.AppStoreのアプリをインストール
AppStoreからインストール


## 10. その他のアプリケーションやドライバをインストール
brew管理に適さないアプリケーションは個別にインストール

