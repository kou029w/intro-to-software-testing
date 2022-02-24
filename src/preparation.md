# 事前準備

JestはNode.js上で実行します。
まずはじめにNode.jsをインストールしましょう。

## Node.jsのインストール

いくつか方法がありますが、[Node.jsの公式サイト](https://nodejs.org)を参照するのがよいでしょう。
プロキシが存在する環境では、追加で下記の設定を行う必要があります。

### NPMのプロキシの設定

確認:

プロキシが存在する環境では、ターミナルで `npm` コマンドを実行した際、次のようなエラーメッセージとともに失敗することがあります。

```console
$ npm install --save-dev jest
npm ERR! code ENOTFOUND
npm ERR! syscall getaddrinfo
npm ERR! errno ENOTFOUND
npm ERR! network request to https://registry.npmjs.org/jest failed, reason: getaddrinfo ENOTFOUND proxy.example.com
npm ERR! network This is a problem related to network connectivity.
npm ERR! network In most cases you are behind a proxy or have bad network settings.
npm ERR! network
npm ERR! network If you are behind a proxy, please make sure that the
npm ERR! network 'proxy' config is set properly.  See: 'npm help config'

npm ERR! A complete log of this run can be found in:
npm ERR!     /home/webdino/.npm/_logs/2022-01-12T07_20_33_146Z-debug-0.log
```

このようなエラーが出る場合は、環境変数 `HTTP_PROXY` と `HTTPS_PROXY` に適切なプロキシのURLを設定します。
一方、このようなエラーが出ない場合は、下記の設定は不要です。必要に応じて行いましょう。

設定項目:

| 環境変数    | 値                       | 例                                      |
| ----------- | ------------------------ | --------------------------------------- |
| HTTP_PROXY  | httpプロキシのURLを入力  | http://user:pass@proxy.example.com:8080 |
| HTTPS_PROXY | httpsプロキシのURLを入力 | http://user:pass@proxy.example.com:8080 |

これらはあくまで例です。実際には自分の環境の設定に合わせて変更する必要があります。

Bash の例:

```bash
echo 'export HTTP_PROXY=http://user:pass@proxy.example.com:8080' >> ~/.bashrc
echo 'export HTTPS_PROXY=http://user:pass@proxy.example.com:8080' >> ~/.bashrc
. ~/.bashrc
```

Windows の例:

「[windows ユーザー環境変数 設定](https://www.google.com/search?q=windows+%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%92%B0%E5%A2%83%E5%A4%89%E6%95%B0+%E8%A8%AD%E5%AE%9A&oq=windows+%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%92%B0%E5%A2%83%E5%A4%89%E6%95%B0+%E8%A8%AD%E5%AE%9A)」でGoogle検索。

別の方法: 環境変数ではなく `npm config` を使う例:

```bash
npm config -g set proxy http://user:pass@proxy.example.com:8080
npm config -g set https-proxy http://user:pass@proxy.example.com:8080
```

## ターミナルの使用

コマンドを実行するにはターミナルを使用します。

macOS の場合:

[アプリケーション] > [ユーティリティ] 内にある [ターミナル] を選択して起動します。

Windows の場合:

Microsoft Storeから、Windows Terminalをインストールします。
インストール後、[スタートメニュー] > [Windows Terminal] を選択して起動します。

## Node.jsの使用

確認:

```bash
node -v
```

ターミナルで実行します。
インストールしたNode.jsのバージョンが表示されていれば、Node.jsを使用する準備は完了です。

```console
$ node -v
v16.14.0
```

## プロジェクトの作成

Node.jsを使ったプロジェクトは、基本的に `package.json` というファイルが配置されます。
`package.json` には、次のようなプロジェクトに必要な付帯情報が含まれます。

- 名前とバージョン
- 外部モジュールや依存関係
- テストやビルドするためのコマンドなど

Node.jsを使った開発をはじめるにあたって、最初にプロジェクトのためのディレクトリを作成します。

```bash
mkdir my-project
cd my-project
```

そして、その中に `package.json` を配置します。

```bash
npm init -y
```

ひととおり準備ができました。
