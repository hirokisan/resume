# a certain company X, 2018-12 ~

Role: Software Engineer

Task: SaaS型WEBマーティングツール開発

Technical Stack: Go,OpenAPI,MongoDB,Elasticsearch,AWS

Methodology: Agile

Transaction: B2B

## Technical Stack

Go:
- WebAPI:
  - Scale: 20+APIs
  - Tool: go-swagger,oapi-codegen
- Batch:
  - Scale: 50+Batches
  - Type: cron,interval,event

MongoDB: Simple Use
- CRUD Database/Collection/Document/Index

Elasticsearch: Simple Use
- CRUD Index/Document

AWS: Simple Use

## Experience

Job Interview: a few times

Onboarding: a few times

Code Review: as daily work

Development: as daily work
- Type:
  - Feature: 10+Projects
  - Debt:
    - [MongoDBのGoクライアント移行](./replace-mongodb-go-client/README.md)
    - [WebAPIフレームワーク移行](./replace-web-api-framework/README.md)
- Responsibility: 要件確認,仕様整理,タスク化,設計,実装,テスト,運用

## Action & Result

### Job Interview

Situation: スクラムチームにジョインするエンジニアを採用する

Problem: エンジニア採用のミスマッチ
- 現場が求めるエンジニアが採用できておらず、期待の合わないエンジニアを採用していた。
- 結果として、ジョイン後に期待値が擦り合わず、チームもジョインしたエンジニアも疲弊するという状態になっていた。

Hypothesis:
- 現場がエンジニアに求める要件が募集要項に反映されていない
  - 募集要項がメンテナンスされていないため
- 採用面談において、現場のエンジニア観点でのフィルタリングが機能していない
  - 現場のエンジニアが面談に参加していなかったため

Action:
- 採用システムの課題を提起した
  - 継続的に採用システムが改善されるような営みが組み込まれているべきであると考えたため
- 採用面談に参加させてもらうように働きかけた
  - 採用面談に参加してチームの期待するエンジニアであるかどうかを確認する質疑応答を行った
- 募集要項を見直すように働きかけた

Result:
- 取り組み中

### Onboarding

Situation: Onboardingが仕組み化されておらず、手探りでジョインしている

Problem: 時間コスト削減、品質一定化

Action:
- ドキュメントを整備した
  - チームメンバーとして知っておくべき情報を記載
- 手順を設計した
  - ジョインから完了までのタスクとフローを用意
- 担当者による継続的な改善を組み込む
  - 新規メンバーのジョイン時に担当者が手順とドキュメントを改善する

Result: 6ヵ月程度かかっていたが、1.5ヵ月程度に短縮された。情報連携の漏れが減った。

### Development

Difficulty: コードベースが複雑である
- 既存の設計を理解して、設計に準拠する形で実装することが求められる
- 技術的な負債が蓄積し始めている

Action:
- 既存の設計を十分に理解する
  - Feature Projectに取り組む
  - 運用に取り組む
- コードベースを整理する
  - 依存関係を整理する
  - 不要なコードを削除する
- Code Reviewする
  - 既存の設計理解を促進する
  - コードベースの秩序を保つ

Result:
- 設計を理解して開発スピードが格段にあがった
  - 1年くらいかかった
- コードベース全体に影響を与えるようなリファクタリングに取り組めるようになった