# README

## usersテーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| name               | string     | null: false                    |
| email              | string     | null: false, unique: true      |
| encrypted_password | string     | null: false                    |


### Association

- has_many :cooks
- has_many :comments




## cooksテーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| name               | string     | null: false                    |
| genre_id           | integer    | null: false                    |
| user               | references | null: false, foreign_key:true  |

### Association

- belongs_to :user
- has_many :comments





## commentsテーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| text               | text       |                                |
| user_id            | references | null: false, foreign_key:true  |
| cooks_id           | references | null: false, foreign_key:true  |

### Association

- belongs_to :user
- belongs_to :cook