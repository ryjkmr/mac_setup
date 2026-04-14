# 新規Macセットアップ手順 2026.04


## ユーザーデータの転送

- 新旧Mac同士をThunderboltで接続。それぞれに電源。

- 新mac起動後、セットアップを移行アシスタントのところまで進める
- 旧Macに移行アシスタントを開く通知が来る
- 通知をクリックして旧Macで移行アシスタントを開く
- 転送設定で「他のMacへ」を選ぶ
- アカウントとネットワーク設定、アクセス権だけ転送
（アプリケーションやその他のファイルを外す）

- 転送終了まで待機

## Apple ID、Google IDを有効化

- 新Mac再起動後、Mac本体のログインパスワードを設定、指紋登録、AppleIDへ二要素認証

- メールアカウントは再現される。ただしGoogleへは再ログインが必要。メールアカウントの「！」をクリック。案内に従ってブラウザが起動したらパスキーでログインすればOK

## Homebrewを使った基本アプリの自動インストール

- App Storeにログイン。Xcodeをインストール
- 一度Xcodeを起動して規約的なものを承諾
- ターミナルでgit —-versionするとXcodeのgitをインストールもしくは起動できる
- DocumentフォルダにgithubのこのリポジトリをクローンしてBrewfileを入手する
```
git clone git@github.com:ryjkmr/mac_setup.git
```

- homebrewをインストール

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

- インストール後に表示される指示に従ってhomebrewへのパスを通す
- githubからクローンしたディレクトリ内でbrewコマンドを実行
```
 brew bundle　
```
- Brewfileに登録してあるアプリが自動的にインストールされる

## Brewでインストールした1PasswordとDropboxの有効化

- 1Passwordを起動、移行アシスタントのお陰か、パスワードを入れるだけで使えた
- Dropboxを起動、パスキーでログイン。移行ツールでDropboxフォルダは転送されているが、いったん同期が行われるのを待つ。同期フォルダの選択ダイアログは無視して良い。フォルダのオフライン・オンライン設定も移行されるらしい
- Chromeを起動、Googleアカウントにパスキーでログイン
- Spotifyを起動、QRコードをスマホ読み取りでログイン
- Arfred。起動して設定。
- Dockの一部のアイコンが「？」になっているが、各アプリをインストール後にクリックして起動するとアイコンが表示されるようになる


## git設定
- homebrew gitへのパスを通す
` ~/.zshrc` に以下を追記

```
export PATH="/opt/homebrew/opt/git/bin:$PATH"
```

- gitのデフォルトブランチをmainに

```
git config --global init.defaultBranch main
```

## node.js設定

- nvmはBrewでインストール済
- nvmの有効化

```
mkdir ~/.nvm
```

- ~/.zshrc に追加
```
export NVM_DIR="$HOME/.nvm"
source "$(brew --prefix nvm)/nvm.sh"
```

- nodeをインストール
```
nvm install --lts
```




## App Storeで必要なアプリを再インストール

- DaVinci Resolve
- 1Password for safari
- LanScan
- Xcode
- Scrivener3
- Notability
- LINE
- Moises
- 紀伊国屋書店Kinoppy
- Kindle
- iReal Pro

## その他のアプリを個別インストーラーでインストール
- Lacaille
- AudioHijack
- Loopback
- Fission
- Affinity
- OBS
- MS Word/Excel/PowerPoint
- Scrivener
- Evernote
- OmniDiskSweeper
- BambuStudio
- Autodesk Fusion
- Qfinder Pro
- Codex
- ATOK


## ハードウエアドライバ関係をインストール
- Brother Printer
- TourBox
- Elgato Stream Deck
- ScanSnap
- CZUR Shine
- ステアーマウス


## ローカル化したWebアプリやサービス
- 移行アシスタントで転送されていた。再認証で使えた
- サービスも移行アシスタントで転送されていた

