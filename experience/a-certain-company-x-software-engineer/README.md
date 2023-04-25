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
    - [MongoDBのGoクライアント移行](../replace-mongodb-go-client/README.md)
    - [WebAPIフレームワーク移行](../replace-web-api-framework/README.md)
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
- エンジニア採用に現場やチームの要求が反映されるようになった
- チームが求めるようなエンジニアがジョインしてくれた

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

#### 複雑なコードベース

Difficulty: コードベースが複雑である
- 既存の設計を理解して、設計に準拠する形で実装することが求められる
- 技術的な負債が蓄積し始めている

Action:
- 既存の設計を十分に理解する
  - Feature Projectに取り組む
  - 運用保守に取り組む
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

#### UAからGA4移行

Difficulty:
- GA4 API割り当て上限

Action:
- GA4 API用にProxy Serverを用意する
- GA4側で確定したデータのリクエスト/レスポンスをキャッシュする

Result:
- 1時間当たりのAPI割り当て上限に当たった場合であっても、次回以降にキャッシュを利用することでインクリメンタルなデータ取得が可能になった

#### テストで振る舞いを示す

Difficulty:
- 英語で頑張ってテストの説明が書かれており、可読性が低い
- 振る舞いではなく、無機質なケースがテストになっている

Action:
- テストでは振る舞いを示し、その振る舞いが担保されるように書く

Result:
- 振る舞いを示すテストを書く人が増えてきた
- 振る舞いを示すテストが増えてきた
- 振る舞いを変更せずに、実装をリファクタリング可能な状態ができてきた

#### 複数人での並行開発

Difficulty:
- コードベースへの理解に大きな差がある開発者が複数人で開発を行う
- 要件を詰め、設計に落とし込んで、コードベースに思想を持って実装していくことが可能な開発者とサポートが必要な開発者がいる

Action:
- まずはアイテムの要件を詰め、その過程で大枠の設計方針を固め、タスクに分割する
- 各タスクに、アサインされた開発者が自走して完了可能な程度の情報を記載する
- また、並行開発の土台を整えるため、基盤となる実装を予め済ませておく

Result:
- サポートが必要な開発者が道に迷うことなく、焦点を当てて取り組むべきポイントが明確になることで、タスク消化が進んだ
- 基盤部分を予め実装しておくことで、互いの作業が干渉せずに開発が進んだ
  - あえて実装すべき部分のI/Fを明示しておくことで、大きく道を外れた実装になることを防ぎ、一定想定された実装が得られた
