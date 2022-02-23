# Jestの機能

Jestの代表的な機能を紹介します。

## Matcher

マッチャー (matcher) とは、与えた値を検証するためのメソッドです。

### 同一性の検証

- `toBe` … 与えた値との同一性 (`===`) を検証します
- `toEqual` … オブジェクトまたは配列のすべてのプロパティの同一性を再帰的に検証します

### 真偽値とそれに類する値の検証

- `toBeNull` … null
- `toBeUndefined` … undefined
- `toBeDefined` … undefined でない (つまり `not.toBeUndefined` と等価)
- `toBeTruthy` … if ステートメントが真であるとみなすもの
- `toBeFalsy` … if ステートメントが偽であるとみなすもの

### 数値

- `toBeGreaterThan` … >
- `toBeGreaterThanOrEqual` … >=
- `toBeLessThan` … <
- `toBeLessThanOrEqual` … <=
- `toBeCloseTo` … 浮動小数点数の丸め誤差を考慮した同一性

### 文字列

- `toMatch` … 正規表現のパターン

### 配列と反復可能なオブジェクト

- `toContain` … 配列や反復可能なオブジェクトに特定のアイテムが含まれているかを検証します

### 例外

- `toThrow` … 例外を発報するかどうかを検証します

### その他

より詳しい情報は [Jest公式リファレンス](https://jestjs.io/ja/docs/expect) を参照してください。

## Promise

Jestは、`test` に渡す関数の前に `async` キーワードを記述するだけで、非同期テストを実行できます。

より詳しい情報は [Jest公式ドキュメント Async/Await](https://jestjs.io/ja/docs/asynchronous#asyncawait) を参照してください。

## beforeEach と afterEach

`beforeEach` と `afterEach` を使用することでテストの実行の前に繰り返し行う準備や、後片付けの処理を宣言できます。

より詳しい情報は [Jest公式ドキュメント セットアップと破棄](https://jestjs.io/ja/docs/setup-teardown) を参照してください。
