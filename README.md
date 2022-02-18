---
title: ソフトウェアテスト概論
marp: true
paginate: true
---

# ソフトウェアテスト概論

WebDINO Japan エンジニア
[渡邉浩平](https://github.com/kou029w)
![w:200](https://github.com/kou029w.png)

---

## テスト

品質の評価

![bg right:69%](https://i.gyazo.com/51f6e0a850e1f40da704b14f3c0db3dc.jpg)

<!-- _footer: 画像: 最初期のコンピューターのバグ (1947) https://americanhistory.si.edu/collections/search/object/nmah_334663 -->

---

## テスト

品質を評価することでより良いサービスの提供を目指す

> ソフトウェアが正しく動作しないと、**経済的な損失**、**時間の浪費**、**信用の失墜**など、さまざまな問題が発生し、時には傷害や死亡事故になることもある。ソフトウェアテストはソフトウェアの品質を評価し、運用環境でソフトウェアの故障が発生するリスクを低減する 1 つの手段である。

<!-- _footer: 引用元: JSTQB (2021) http://jstqb.jp/dl/JSTQB-SyllabusFoundation_Version2018V31.J03.pdf 「1.1 テストとは何か？」より -->

---

## 品質

サービスや製品としての価値

開発したサービスや製品によって\
利用者に価値を提供することが目的

![bg right:50%](https://i.gyazo.com/6f612bf15c62fd9b8465bcbe21d4d397.png)

<!-- _footer: 図の出典: 狩野紀昭 (1984)「魅力的品質と当たり前品質」をもとに改変して作成 -->

---

## CI/CD (Continuous Integration and Continuous Delivery)

変更すると決めてからユーザーが使えるようになるまでの一連の継続的な活動

> ![デプロイメントパイプライン](https://i.gyazo.com/96475ee59df81cb75a2e5ca53cba5758.png)

<!-- _footer: 図の出典: David Farley, Jez Humble, 和智 右桂, 高木 正弘 (2017)「継続的デリバリー」 -->

すばやく、繰り返し、頻繁にフィードバックを得ることで最適な品質を保ち続ける

---

## デプロイメントパイプラインとフィードバック

どちらも欠かせない

- 自動化していなければサービスをすばやく利用者に提供できない
- フィードバックがなければ最適なサービスの品質を見極められない

---

## コードとテスト

どちらも欠かせない

- コードが存在しなければサービスを提供できない
- テストが存在しなければ最適なコードの品質を見極められない

---

## ここまでのまとめ

- テストとは品質の評価
- 最適なコードの品質を見極め、改善することでより良いサービスを提供できる

---

## どうやってテストするのか

---

## 前提

まず然るべき品質の確保が最優先事項

実践の方法は現場によって異なるが、\
大切なのは現実の問題に向き合い価値を提供するということ

---

## TDD (Test-Driven Development)

最初からテストをすばやいサイクルで行い続ける設計手法

ウォーターフォール型の重たい方法論からの脱却が背景にある

![w:1200](https://ptuml.hackmd.io/svg/SoWkIImgAStDKIWjJarEB4xbAixEp2j8B4hCXOaeL7CfA2Gb9cUd5-MNvgKav-Va5ocKPsIMf8B4yujIKeiWOaavG4L0iSIYelnoPA5QBYwDvxFNFLinyt7Jf6SRTprkQdpSrAsfe6kdeF6ukUrnqyx7pHqWgTax7ZVsQt9X4uGeRjhyk7dFu-PE975bDpSJCmC3wvpCl5IzfFoS52wioeZMRbsIMb5Y1H5Li5AmIRA3k-RfaetFfawtqK-oms47n4Eh7ZTFVToqy77J-iTD-y7SpO-RDW2jCZ1sT3DtHBSA8ig5HoC5ngBvu5d7XATTyw4-m6qVo49i4ORV1mwfUId0bCG50000)

設計して、すぐ書く、すぐリファクタリングする

テストはコードより先

<!-- _footer: 参考文献: Kent Beck (2002) "Test Driven Development" -->

---

## 「なぜ繰り返しテストを行うか」

現代のソフトウェア開発においてこの問い自体あまり重要でなくなった

なぜなら

- すばやく変化に対応し続けるアジャイルの考え方は技術の進展とともに浸透
- 一方でリリースして終了というウォーターフォール型のプロジェクトは衰退

<!-- _footer: Netflix (2018)の事例: [数時間でのカナリアリリース](https://netflixtechblog.com/full-cycle-developers-at-netflix-a08c31f83249#9868:~:text=Deployments%20are%20routine%20and%20frequent%2C%20canaries%20take%20hours%20instead%20of%20days) -->

---

## 何をテストするのか

---

## テストピラミッド

コストに応じた適切な粒度と規模を保つテスト戦略

ユニットテストのような小さなテストを大規模に行い、エンド・トゥ・エンド (E2E) テストのようなコストのかかるテストはできるだけ小規模に保つ

![bg fit right:45%](https://i.gyazo.com/dd948eed8f6c94e7821c92b65e38c960.png)

<!-- _footer: 参考文献: Mike Cohn (2009) "Succeeding With Agile" -->

---

## たとえば

最初に、静的型解析や静的コード解析などゼロコストで始められるものを行う

- サービス: GitHub Actions
- ツール: TypeScript と ESLint

基本的には、ユニットテストなど低コストなテストを行う

- ツール: Jest

実際にサービスを運用していくには、E2E テストなど高コストなテストを行う

- ツール: Playwright

---

## GitHub Actions

GitHub の提供する自動実行環境

https://docs.github.com/ja/actions

---

## GitHub Actions による自動テストの例

`git push` するたびにテストを行う

```yml
# .github/workflows/test.yml
name: test
on: push
jobs:
  main:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
        with: { node-version: lts/*, cache: npm }
      - run: npm ci
      - run: npm test
```

テストだけでなく GitHub の提供する実行環境の上で好きなジョブを実行できる

---

## TypeScript

https://www.typescriptlang.org

Microsoft が開発した JavaScript に型を指定できるようにした言語

> - 新しい記法を使うが、ブラウザの互換性を維持するコードを書く手法としてコンパイラを使うのが当たり前になってきた
> - 大規模になると（小規模でも）、型情報があるとエラーチェックが実装中に行われるので開発がしやすくなる
> - 型を持った JavaScript には TypeScript と flowtype の 2 つがあるが、シェアが高いのが TypeScript
>
> 引用元: 仕事ですぐに使える TypeScript ドキュメント 前書き\
> https://future-architect.github.io/typescript-guide/preface.html

---

## TypeScript を試してみる

https://www.typescriptlang.org/ja/play

---

## ESLint

https://eslint.org

静的コード解析ツール

チェックできることの例

- デッドコードの検知 (no-unused-vars, no-unreachable, etc.)
- コードの複雑さ (max-lines, max-depth, complexity, etc.)

```console
$ npm init @eslint/config # インストール
$ npx eslint --fix .      # 実行と自動修正
```

---

## Jest

https://jestjs.io/ja/

テスティングフレームワーク

```console
$ npm i -D jest # インストール
$ npx jest      # 実行
```

---

## Playwright

https://playwright.dev

Microsoft が開発した E2E テストツール

クロスブラウザー・クロスプラットフォームをサポート

- ブラウザー: Chrome, Firefox, Safari, Opera, Edge
- プラットフォーム: Windows, macOS, Linux, Android, iOS

```console
$ npm i -D playwright @playwright/test                      # インストール
$ npx playwright codegen -o a.test.mjs https://example.com  # テストコードの自動生成
$ npx playwright test                                       # テストの実行
```

---

## ここまでのまとめ

- 何を・どうやってテストするのか
  - TDD … 最初からテストをすばやいサイクルで行い続ける設計手法
  - テストピラミッド … コストに応じた適切な粒度と規模を保つテスト戦略
- テストを実践するための具体的なサービスやツールの紹介

---

## ![h:0.8em][github.svg] フィードバック

[このスライドを編集する](https://github.com/kou029w/intro-to-software-testing/edit/main/README.md) / [問題を報告する](https://github.com/kou029w/intro-to-software-testing/issues/new)

[github.svg]: https://cdnjs.cloudflare.com/ajax/libs/simple-icons/5.7.0/github.svg
