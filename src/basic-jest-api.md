# 基本的な機能

Jestの機能について説明します。

## テストファイルの検出

Jestは、デフォルトで下記のファイルをテストファイルとして検出します。

- `.test.js` ファイル
- `.test.ts` ファイル
- `.spec.js` ファイル
- `.spec.ts` ファイル
- `__tests__` ディレクトリ以下の `.js`、`.ts`、`.jsx`、`.tsx` ファイル

## テストの自動監視

`--watch` オプションを指定することで、テストファイルの変更を自動で監視します。

```bash
npx jest --watch
```

終了するには、キーボードの `q` を押します。

## プロジェクトでのテストコマンドの設定

この設定を行うと、`npm test` コマンドでJestを実行できるようになります。

```bash
npm set-script test jest
```

実行すると、`package.json` には下記のような設定が追加されます。

```json
{
  "scripts": {
    "test": "jest"
  }
}
```

NPMコマンドでのテストの実行:

```bash
npm test
```

`npx jest` コマンドの実行と同様のテスト結果が得られます。
