# テストの作法

テストを書くときの代表的な作法を紹介します。

## Arrange・Act・Assert (AAA) パターン

テストを書くときの作法の1つです。
準備 (Arrange)・実行 (Act)・検証 (Assert) というプロセスで分けて書きます。
準備・実行・検証をそれぞれ分けて書いておくことで比較的読みやすいテストを書くことができます。

例:

```js
test("正しくJSONをパースできる", () => {
  // 準備
  const json = `{"name": "太郎", "age": 20}`;

  // 実行
  const parsed = JSON.parse(json);

  // 検証
  expect(parsed).toEqual({ name: "太郎", age: 20 });
});
```
