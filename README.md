## users

|Column   |Type  |Options                  |
|---------|------|-------------------------|
|nickname |string|null: false, unique: true|
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
