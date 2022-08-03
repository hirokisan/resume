## MongoDBのGoクライアント移行

- 背景
  - MongoDBのGoクライアントとしてgo-mgo/mgoを利用している
  - go-mgo/mgoは既にメンテナンスされていない
- 課題
  - メンテナンスされていないライブラリに依存している
  - go-mgo/mgoのbson依存が各所に生まれている
- 方針
  - go-mgo/mgoの利用をやめる
  - mongodb/mongo-go-driverを利用する
- 取り組み
  - 小さく漸近的に置き換えを進める前提で移行計画を立てる
  - go-mgo/mgoとmongodb/mongo-go-driver双方に対応するbsonをカスタム定義する
    - ObjectIdの型が異なるのでその辺りを調整することになる
  - go-mgo/mgoをforkしてカスタム定義のbsonを受け付けるように処理を調整する
  - ここから漸近的に置き換えていく作業をする
