# テーブル設計

##　users テーブル

| Column               | Type    | Options      |
| -------------------  | ------- |-----------   |
| name                 | storing | null: false  |
| email                | storing | null: false  |
| encarypted_password  | storing | null: false  |

### Association

- has_many  :room_users
- has_many  :room_users, through: :room_users
- has_many  :room_users

##　rooms テーブル

| Column               | Type    | Options      |
| -------------------  | ------- |-----------   |
| name                 | storing | null: false  |

### Association

- has_many  :room_users
- has_many  :room_users, through: :room_users
- has_many  :room_users

## room_users テーブル

| Column              | Type       | Options                          |
| ------------------- | -------    |-----------                       |
| user                | references | null: false 　foreingg_key: ture |
| room                | references | null: false   foreingg_key: ture |

### Association

- belongs_to :room
- belongs_to :user

## messages テーブル

| Column              | Type       | Options                          |
| ------------------- | -------    |-----------                       |
| content             | string     |                                  |
| user                | references | null: false 　foreingg_key: ture |
| room                | references | null: false   foreingg_key: ture |

### Association

- belongs_to :room
- belongs_to :user
