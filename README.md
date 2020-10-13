# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| --------   | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | string | null: false |
| occupation | string | null: false |
| position   | string | null: false |



### Association

- has_many :room_users
- has_many :rooms, through: room_users
- has_many :messages

## prototypes テーブル

| Column      | Type       | Options     |
| ------      | ------     | ----------- |
| title       | string     | null: false |
| catch_copy  | text       | null: false |
| concept     | text       | null: false |
| user        | references | null: false |



### Association

- has_many :room_users
- has_many :users, through: room_users
- has_many :messages

## comments テーブル

| Column      | Type       | Options                        |
| ------      | ---------- | ------------------------------ |
| text        | text       | null: false, foreign_key: true |
| user        | references | null: false, foreign_key: true |
| prototype   | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user




https://tech-master.s3.amazonaws.com/uploads/curriculums//bfa083231a620f9c5406ea31be29b322.png