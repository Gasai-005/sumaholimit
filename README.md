## アプリ名
sumaholimit

## 概要
スマホを使用する際に少しの障害を設けることで、スマホの無駄な使用を抑える

## 制作意図
昨今デジタル機器による能力低下が叫ばれているが、本やネット記事で情報だけ与えられても実行するのは困難だと思った。なぜなら様々なアプリが人の脳の仕組みを利用し依存させているからだ。その呪縛から抜け出すには同等かそれ以上の仕組みが必要だろう。しかし頭の良い”エリート”たちが用いる以上のものを探し出す、または生み出すのは困難だ。しかし機能を付け足し改悪する事はできる。そこでデジタル機器の使用にストレスを感じさせるスマホの使用時間軽減を手助けする為に本アプリの開発を考えた。

## 実装予定
何の為にスマホを使うか入力する
予想使用時間を設定し、実際の使用時間とどれだけ遠いかを確認できる
各行動に点数を与え、登録者のランキングが見られる
ユーザーページで、各カテゴリーの使用割合をグラフで表示

## user

|Column   |Type  |Options                  |
|---------|------|-------------------------|
|nickname |string|null: false              |
|password |string|null: false              |
|email    |string|null: false, unique: true|

### Association
has_many :doing

## doing

|Column      |Type      |Options                        |
|------------|----------|-------------------------------|
|title       |string    |null: false                    |
|description |text      |null: false                    |
|time        |integer   |null: false                    |
|over_time   |integer   |null: false                    |
|user        |references|null: false, foreign_key: true |
|category    |references|null: false, foreign_key: true |
|status_id   |integer   |null: false                    |

### Association
belongs_to :user
has_many :categories

## categories
|Column |Type   |Options     |
|-------|-------|------------|
|name   |string |null: false |

### Association
belongs_to :doing
