# README

## users テーブル

| Column               | Type   | Options     |
| -------------------- | ------ | ----------- |
| email                | string | null: false unique: true |
| encrypted_password   | string | null: false |
| nickname             | string | null: false |

### Association

- has_many :items
- has_many :orders



## plans テーブル

| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| title            | string     | null: false                    |
| start_time        | datetime    | null: false                    |
| end_time     | datetime    | null: false                    |
| location          | text       |                   |
| user           | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :order

## address テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| post_code | string     | null: false,                   |
| area_id   | integer    | null: false                    |
| district  | string     | null: false,                   |
| area_code | string    | null: false,                   |
| building  | string     |                                |
| phone_number   | string    | null: false,               |
| order     | references | null: false, foreign_key: true |

### Association


- belongs_to :order


## orders テーブル

| Orders    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| user      | references | null: false, foreign_key: true |
| item      | references | null: false, foreign_key: true |


### Association

- belongs_to :user
- has_one :address
- belongs_to :item

