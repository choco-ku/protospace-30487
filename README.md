# テーブル設計

## usersテーブル

| Column     | Type   | Options     |
| ---------  | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototpyes
- has_many :comments


## prototpyes テーブル

| Column     | Type      | Options       |
| ---------  | --------  | -----------   |
| title      | string    | null: false   |
| catch_copy | text      | null: false   |
| concept    | text      | null: false   |
| image      |           | ActiveStorage |
| user       | reference | null: false   |

### Association

- has_many :comments
- belongs_to :user


## comments テーブル

| Column     | Type      | Options          |
| ---------  | --------  | --------------   |
| text       | text      | null: false      |
| user       | reference |foreign_key: true |
| prototpye  | reference | foreign_key: true|

### Association

- belongs_to :prototpye
- belongs_to :user
