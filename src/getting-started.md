# はじめてのテスト

ターミナルから `npm` コマンドでJestをインストールします。

```bash
npm i -D jest
```

または

```bash
npm install --save-dev jest
```

いずれかのコマンドを実行することでJestがインストールされます。
ここでインストールしたJestは、このプロジェクトの開発用の依存関係として追加されます。
つまり、これ以降このプロジェクトは `npm install` コマンドを実行することでJestを導入できるようになります。

インストールしたJestは、`npx jest` コマンドを使用することで実行できます。

```bash
npx jest
```

しかし、まだテストが1件も存在しないのでこのコマンドは失敗します。

```console
$ npx jest
No tests found, exiting with code 1
Run with `--passWithNoTests` to exit with code 0
In /home/kou029w/intro-to-software-testing
  11 files checked.
  testMatch: **/__tests__/**/*.[jt]s?(x), **/?(*.)+(spec|test).[tj]s?(x) - 0 matches
  testPathIgnorePatterns: /node_modules/ - 11 matches
  testRegex:  - 0 matches
Pattern:  - 0 matches
```

実際にテストを作成し、実行していきましょう。

次のファイルを作成します。

```js
// hello.test.js
test("1と2の合計は3です", () => {
  expect(1 + 2).toBe(3);
});
```

この作成した `hello.test.js` は、`npx jest` コマンドを実行するときにテストとして実行されるようになります。

```console
$ npx jest
 PASS  ./hello.test.js
  ✓ 1と2の合計は3です (1 ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        0.204 s
Ran all test suites.
```

問題なく実行できましたか？
気付いた人もいるかと思いますが、

```
 PASS  ./hello.test.js
```

とあるのは、「テスト `hello.test.js` が実行され、そのテストは合格 (pass) しました」ということを意味します。

このようにしてJestは簡単にテストを行うことができます。

## はじめてのテストのコードの説明

テストのコードについてより詳しく説明します。

はじめてのテストのコード:

```js
test("1と2の合計は3です", () => {
  expect(1 + 2).toBe(3);
});
```

このコードは、「1と2の合計は3です」というテストを意味します。
式 `1 + 2` が、 `3` と等しいことを検証するテストです。
下記のJestの機能が使われています。

`test()` 関数

テストを宣言するための関数です。

- 第一引数には、このテストの説明を人間が読める形式で記述します
- 第二引数には、テストの本体を記述します

`expect()` 関数

引数に与えた値をテストします。

`.toBe()` メソッド

与えた値との同一性を検証します。

このコードは、Jestの基本的な機能を確認するための極めて単純なテストですが、テスト環境自体の検証を行うことでもあります。
テスト環境の検証は、テストを行う上で最初に確認しておく重要なポイントです。
