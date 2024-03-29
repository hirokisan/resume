## WebAPIフレームワーク移行

- 背景
  - forkしたgo-swaggerに変更を加えて利用している
  - fork元の変更を取り込む対応はできていない
- 課題
  - fork元の変更に追従できていない
  - go-swaggerにより生成されたGoコードが散らばっている
    - 不要な依存が各所に生まれている
- 方針
  - forkしたgo-swaggerの利用をやめる
  - oapi-codegenを利用する
- 経緯
  - OpenAPIという形でAPI定義を利用者と共有している
    - このI/Fを変更する必要性は特になく、変更しない利点が大きい
  - API GatewayでOpenAPIを割り当てる手もありそう
  - oapi-codegenがgo-swaggerの代替として使えそう
    - 現状のOpenAPI v2をv3に変換すればoapi-codegenでも使える
  - oapi-codegenが課題の解決として手軽そう
  - 試験的に既存APIの置き換えに取り組んだ
    - 現実的な移行手順が描けた
    - 既存のgo-swagger生成のGoコード依存の整理も副次的に実現できる
- 工夫
  - API(xxx.yaml)単位で置き換えるのではなく、method単位やcontroller(tags)単位で置き換え可能にする
    - 既存handlerと新規handlerを併存させ、http middlewareでリクエストを振り分けるようにした
  - 既存のv2定義をv3に変換して利用する
    - nullableの扱いが異なるため、デフォルトでnullable:trueとして扱われるように処理を加える
    - integer/numberの扱いが異なるため、変換後のv3定義にformatを明記する
  - 移行作業の手順をドキュメントとして用意しておく
  - 利用者側に移行による影響を与えない、既存の挙動を変えない
- 成果
  - forkしてメンテナンスしていないgo-swaggerの利用をやめられる
  - OpenAPIのv3を利用する土台ができる
  - API(UI)向けの型依存が局所化される
  - API(UI)付近に配置されていたコアなロジックが一定のコンテキストにおいて利用可能な形に再配置される
