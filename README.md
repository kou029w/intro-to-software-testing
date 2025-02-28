---
title: ソフトウェアテスト概論
marp: true
paginate: true
---

# ソフトウェアテスト概論

WebDINO Japan シニアエンジニア
[渡邉浩平](https://github.com/kou029w)
![w:200](https://github.com/kou029w.png)

---

## テスト

品質の評価

![bg right:69%](https://i.gyazo.com/51f6e0a850e1f40da704b14f3c0db3dc.jpg)

<!-- _footer: 画像: 最初期のコンピューターのバグ (1947) https://americanhistory.si.edu/collections/search/object/nmah_334663 -->

---

## テスト

より良い製品の提供を目指すために品質を評価する

> ソフトウェアが正しく動作しないと、経済的な損失、時間の浪費、信用の失墜など、さまざまな問題が発生し、時には傷害や死亡事故になることもある。ソフトウェアテストはソフトウェアの品質を評価し、運用環境でソフトウェアの故障が発生するリスクを低減する 1 つの手段である。

<!-- _footer: 引用元: JSTQB (2021) http://jstqb.jp/dl/JSTQB-SyllabusFoundation_Version2018V31.J03.pdf 「1.1 テストとは何か？」より -->

---

## 品質

製品としての価値

![bg fit right:50%](https://i.gyazo.com/e5bb4f2e0b19f624e3be42bf3d9ae63f.png)

<!-- _footer: 図の出典: 狩野紀昭 (1984)「魅力的品質と当たり前品質」をもとに改変して作成 -->

---

## 検証

- 正しく製品を作っているか
- 開発者のためのテスト

## 妥当性確認

- ビジネスとして妥当か
- 利用者のためのテスト

![bg fit right:55%](https://i.gyazo.com/e1d3e165c1eba7ddbc7e2cae86bb5b5e.png)

<!-- _footer: 図の出典: "The difference between Verification and Validation" https://www.easterbrook.ca/steve/2010/11/the-difference-between-verification-and-validation/ をもとに改変して作成 -->

---

## ソフトウェアテストの実践

- 自動テスト
- テスト駆動開発
- 継続的インテグレーション・継続的デリバリー

---

## 自動テスト

自動化されたテストプロセス

```js
import { expect, test } from "vitest";
import isLeapYear from "./isLeapYear";

test("西暦年号が4で割り切れる年はうるう年", () => {
  expect(isLeapYear(2024)).toBe(true);
});
```

---

## 自動テスト

ソフトウェアの内部品質への投資の損益分岐点は1ヶ月以内[^1]

時間と労力を節約し効率的な品質保証を可能にする

自動テストに必要な2つの性質

- Self-Validating（自己検証可能）
- Repeatable（繰り返し可能）

[^1]: https://speakerdeck.com/twada/quality-and-speed-2020-spring-edition?slide=63

<!-- _footer: 参考文献: [保守しやすく変化に強いソフトウェアを支える柱　自動テストとテスト駆動開発、その全体像 ～Software Design 2022年3月号「そろそろはじめるテスト駆動開発」より | gihyo.jp](https://gihyo.jp/article/2024/01/automated-test-and-tdd) -->

---

## テスト駆動開発 (TDD)

最初からテストをすばやいサイクルで行い続ける設計手法

ウォーターフォール型の重たい方法論からの脱却が背景にある

![w:1200](https://ptuml.hackmd.io/svg/SoWkIImgAStDKIWjJarEB4xbAixEp2j8B4hCXOaeL7CfA2Gb9cUd5-MNvgKav-Va5ocKPsIMf8B4yujIKeiWOaavG4L0iSIYelnoPA5QBYwDvxFNFLinyt7Jf6SRTprkQdpSrAsfe6kdeF6ukUrnqyx7pHqWgTax7ZVsQt9X4uGeRjhyk7dFu-PE975bDpSJCmC3wvpCl5IzfFoS52wioeZMRbsIMb5Y1H5Li5AmIRA3k-RfaetFfawtqK-oms47n4Eh7ZTFVToqy77J-iTD-y7SpO-RDW2jCZ1sT3DtHBSA8ig5HoC5ngBvu5d7XATTyw4-m6qVo49i4ORV1mwfUId0bCG50000)

テストはコードより先

設計して、すぐ書く、すぐリファクタリングする

<!-- _footer: 参考文献: Kent Beck (2002) "Test Driven Development" -->

---

## コードとテスト

どちらも欠かせない

- コードが存在しなければシステムを提供できない
- テストが存在しなければ最適なコードの品質を見極められない

---

## 継続的インテグレーション・継続的デリバリー (CI/CD)

変更を決めてからその変更が利用者に提供されるまでの一連の継続的な活動

![w:1080](https://ptuml.hackmd.io/svg/LP7DIiD058NtynGnk6WN-WOfVP1kGZCbmMIcJ2OBbyxrfr9HYuWegD2WGiML1ItuDfUqzIsScyHgO60EvtpSEPVffjfNEajY9-33MEudN6YMxaLYw2i_SH8fP3zKCk6ELXbdMzk3IANQStiCpJl28m8WZD0i48uHlj1yzeJDu1bXN6Sse7X4mVVzxUhkSFsIBnykA_0AuHNXrBMZKzwN8l3SzSci65yN5pTuC2cEdj2SRMOGfiD8RIWqRmWvmWJDHqdb3NOWCwL3prsUJrVpgNswaSO-hO8mAuyjlt1PgzgmlTDfrONQRADsEx_ndqTWMOcyIZImoYAgAaDUhHfSxH58lSWgxtzGbul0VXNx0G00)

デプロイメントパイプラインによる自動化

すばやく、繰り返し、頻繁にフィードバックを得ることで最適な品質を保ち続ける

<!-- _footer: 図の出典: David Farley, Jez Humble, 和智 右桂, 高木 正弘 (2017)「継続的デリバリー」図1-1をもとに改変して作成 -->

---

## デプロイメントパイプラインとフィードバック

どちらも欠かせない

- 自動化していなければシステムをすばやく利用者に提供できない
- フィードバックがなければ最適なシステムの品質を見極められない

---

## 世界は不確実

![bg right:62% 将来ほど予報円が大きく予測困難](https://www.jma.go.jp/jma/kishou/know/typhoon/7-1-1.png)

<!-- _footer: 図の出典: 気象庁 https://www.jma.go.jp/jma/kishou/know/typhoon/7-1.html -->

将来ほど予測困難

---

## ソフトウェア開発は不確実

コストは予測困難

![bg right:60% fit Barry W. Boehm (1984)](https://i.gyazo.com/81c2b1a3fdd1eb46ee4f612bd6bef742.png)

<!-- _footer: 図の出典: Barry W. Boehm (1984) "Software Engineering Economics" doi.org/10.1109/TSE.1984.5010193 Fig.3 -->

---

## 現代のソフトウェア開発

- **変化の加速**: 技術革新や市場の需要は急速に変化しており予測可能性は低下
- **エコシステムの複雑化**: マイクロサービス、クラウド、モバイル、IoTなど、多様な技術が絡み合うことで、システム全体の複雑さは増加
- **利用者中心の要求**: ユーザーエクスペリエンスの重要性が高まり、迅速なフィードバックループを通じた継続的な改善が求められるように

なぜテストを行うか

- より良い品質の製品を提供するために、品質を見極め、改善し続けるため

<!-- _footer: Netflix (2018)の事例: [数時間でのカナリアリリース](https://netflixtechblog.com/full-cycle-developers-at-netflix-a08c31f83249#9868:~:text=Deployments%20are%20routine%20and%20frequent%2C%20canaries%20take%20hours%20instead%20of%20days) -->

---

## ここまでのまとめ

- テストとは品質の評価
- より良い品質の製品を提供するために、品質を見極め、改善し続ける
- 自動テスト … 自動化されたテストプロセス
- TDD … 最初からテストをすばやいサイクルで行い続ける設計手法
- CI/CD … デプロイメントパインプラインによって提供を行う一連の継続的な活動

---

## 何を・どうやってテストするのか

---

## 前提

まず然るべき品質の確保が最優先事項

実践の方法は現場によって異なるが、\
大切なのは現実の問題に向き合い価値を提供するということ

---

## 自動テストが持つべき性質

- Independent/Isolated（独立している）
- Fast（高速である）

<!-- _footer: 参考文献: [保守しやすく変化に強いソフトウェアを支える柱　自動テストとテスト駆動開発、その全体像 ～Software Design 2022年3月号「そろそろはじめるテスト駆動開発」より | gihyo.jp](https://gihyo.jp/article/2024/01/automated-test-and-tdd) -->

---

## 自動テストの理想的な状態

- 誰が書くか … テスト対象のコードを書いた本人が
- いつ書くか … テスト対象のコードを書くとき
- どのくらい書くか … ムリなく・ムダなく・ムラなく
- どのくらいの頻度で実行するか … すぐに

<!-- _footer: 参考文献: [保守しやすく変化に強いソフトウェアを支える柱　自動テストとテスト駆動開発、その全体像 ～Software Design 2022年3月号「そろそろはじめるテスト駆動開発」より | gihyo.jp](https://gihyo.jp/article/2024/01/automated-test-and-tdd) -->

---

## たとえば

静的コード解析や静的型解析などすぐに始められるものを行う

- ESLint
- TypeScript

自動実行環境やテスティングフレームワークを使い繰り返し高速にテストを行う

- GitHub Actions
- Vitest
- Playwright

---

## ESLint

https://eslint.org

JavaScript の静的コード解析ツール

チェックできることの例

- デッドコードの検知 (no-unused-vars, no-unreachable, etc.)
- コードの複雑さ (max-lines, max-depth, complexity, etc.)

```console
$ npm init @eslint/config # インストール
$ npx eslint --fix .      # 実行と自動修正
```

---

## ESLint を試してみる

https://eslint.org/play/

---

## TypeScript

https://www.typescriptlang.org

Microsoft が開発した JavaScript に型を指定できるようにした上位互換言語

> 大規模になってくると、型があるとコーディングが楽になります。型を書く分の手間は多少増えますが、昔の静的型付き言語と異なり、TypeScriptは「明示的に型がわかる場面」では型を省略して書くことができます。また、動的なオブジェクトなど、JavaScriptでよく登場する型もうまく扱えるように設計されています。そのような使い勝手の良さもあり、現在は採用数が伸びています。有名なOSSも実装をTypeScriptに置き換えたり、企業でも積極的な活用が進んでいます。
> ―― https://future-architect.github.io/typescript-guide/preface.html

<!-- _footer: 引用元: Future Corporation (2019-2020)「仕事ですぐに使えるTypeScript」前書きより -->

---

## TypeScript を試してみる

https://www.typescriptlang.org/ja/play

---

## GitHub Actions

GitHub の提供する自動実行環境

https://docs.github.com/ja/actions

---

## GitHub Actions による自動テストの例

`git push` するとテストを実行する例

```yml
# .github/workflows/test.yml
name: test
on: push
jobs:
  main:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: "lts/*"
          cache: npm
      - run: npm ci
      - run: npm test
```

テストだけでなく GitHub の提供する実行環境の上で好きなジョブを実行できる

---

## Vitest

https://vitest.dev/

ESM, TypeScript, JSX のテストを行うためのフレームワーク

```console
$ npm i -D vitest # インストール
$ npx vitest      # 実行
```

---

## Vitest を試してみる

<iframe
  src="https://stackblitz.com/github/kou029w/vitest-hands-on/tree/main/templates/template?embed=1&view=editor&terminal=watch&file=sum.js,sum.test.js"
  style="
    width: 100%;
    height: 640px;
    border: 0;
    border-radius: 4px;
    overflow: hidden;
  "
  title="template"
></iframe>

---

## Playwright

https://playwright.dev

Microsoft が開発した E2E テストを行うためのフレームワーク

クロスブラウザー・クロスプラットフォームをサポート

- ブラウザー: Chromium, WebKit, Firefox
- プラットフォーム: Windows, macOS, Linux

```console
$ npm i -D playwright @playwright/test                      # インストール
$ npx playwright codegen -o a.test.mjs https://todomvc.com  # テストコードの自動生成
$ npx playwright test --headed                              # テストの実行
```

---

## Playwright を試してみる

https://try.playwright.tech

---

## まとめ

- 何を・どうやってテストするのか
- テストを実践するための具体的なツールの紹介
  - ESLint … JavaScript 静的コード解析ツール
  - TypeScript … JavaScript 上位互換言語
  - GitHub Actions … 自動実行環境
  - Vitest … JavaScript テストフレームワーク
  - Playwright … E2E テストフレームワーク

---

# ハンズオン

---

## Vitestではじめるテスト

https://kou029w.github.io/vitest-hands-on/

---

## ![h:0.8em][github.svg] フィードバック

[このスライドを編集する](https://github.com/kou029w/intro-to-software-testing/edit/main/README.md) / [問題を報告する](https://github.com/kou029w/intro-to-software-testing/issues/new)

[github.svg]: https://cdnjs.cloudflare.com/ajax/libs/simple-icons/5.7.0/github.svg

---

## 過去のハンズオン資料: Jestではじめるテスト

https://kou029w.github.io/jest-hands-on/

<script>
window.addEventListener("DOMContentLoaded", function () {
  document.querySelectorAll("a")?.forEach(function (a) {
    a.setAttribute("target", "_blank");
    a.setAttribute("rel", "noreferrer");
  });
});
</script>
<style>
footer {
  overflow-wrap: anywhere;
}
</style>
