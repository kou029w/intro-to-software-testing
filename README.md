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

## なぜテストをするのか

---

## 品質

品質とは製品としての価値

---

## <ruby>狩野<rp> (</rp><rt>かのう</rt><rp>)</rp></ruby>モデル

![bg right:60% fit](https://i.gyazo.com/6f612bf15c62fd9b8465bcbe21d4d397.png)

顧客の求める品質のモデル

<!-- _footer: 図の出典: 狩野紀昭 (1984)「魅力的品質と当たり前品質」をもとに改変して作成 -->

---

## 魅力的品質と当たり前品質

魅力的品質についてはみなさんが考えてほしい

ソフトウェア開発における当たり前品質に関するヒントをご紹介します

---

## CI/CD (Continuous Integration and Continuous Delivery)

変更すると決めてからユーザーが使えるようになるまでの一連の継続的な活動

「サイクルタイムを短く、品質を高く」

> ![デプロイメントパイプライン](https://i.gyazo.com/96475ee59df81cb75a2e5ca53cba5758.png)

<!-- _footer: 図の出典: David Farley, Jez Humble, 和智 右桂, 高木 正弘 (2017)「継続的デリバリー」 -->

品質: 最適なレベルに保つ
手段: 自動化し機械によって繰り返す、頻繁なフィードバックを得る

---

## 自動化とフィードバック

どちらも欠かせない

なぜなら…

- 自動化していなければ素早く変更を反映させられない
- フィードバックが得られなければ最適な品質を見極められない

---

## テスト

品質の評価

---

## テストピラミッド

Mike Cohn によって提唱

コストに応じた適切な粒度で行う\
テスト戦略

![bg right fit](https://i.gyazo.com/dd948eed8f6c94e7821c92b65e38c960.png)

<!-- _footer: 参考文献: Mike Cohn (2009) "Succeeding With Agile" -->

---

## まとめ

- 品質とは製品としての価値
- 品質を高めるヒント … CI/CD、テスト

---

## 便利な CI/CD サービスとテストツール

JavaScript と TypeScript での開発を支える便利なツールの紹介

---

## 実行環境

CI/CD を実現するための環境

- 手元のパソコン
- [GitHub Actions](https://github.co.jp/features/actions)
- [CircleCI](https://circleci.com/ja/)

---

## テストフレームワーク

テストをサポートするための一連のツール

- [Jest](https://jestjs.io/ja/)
- [Mocha](https://mochajs.org/)
- [Tape](https://github.com/substack/tape)

---

## E2E テストツール

Web ブラウザーの操縦を自動化するためのツール

- [Puppeteer](https://pptr.dev/)
- [Playwright](https://playwright.dev/)
- [Selenium](https://www.selenium.dev/selenium/docs/api/javascript/index.html)

---

## 他

- 型システム … [TypeScript](https://www.typescriptlang.org/)
- 静的解析ツール … [ESLint](https://eslint.org/)
- UI を確認するためのショーケースツール … [Storybook](https://storybook.js.org/)
- 依存関係の自動更新 … [Renovate](https://www.whitesourcesoftware.com/free-developer-tools/renovate/)
- セキュリティ監査 … [LGTM](https://lgtm.com/)、[Snyk](https://snyk.io/)
- コンプライアンス監査 … [FOSSA](https://fossa.com/)

---

## まとめ

JavaScript と TypeScript での開発を支える便利なツールを紹介

---

## 後付

---

## 話していないこと

- ソフトウェア設計技法
- テスト設計技法
- リファクタリング

---

## ![h:0.8em][github.svg] フィードバック

[このスライドを編集する](https://github.com/kou029w/intro-to-software-testing/edit/main/README.md) / [問題を報告する](https://github.com/kou029w/intro-to-software-testing/issues/new)

[github.svg]: https://cdnjs.cloudflare.com/ajax/libs/simple-icons/5.7.0/github.svg
