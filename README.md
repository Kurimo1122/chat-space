# DB設計

## users table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|group_id|integer|foreign_key: true|
|message_id|integer|foreign_key: true|

### Association
- has_many :groups
- has_many :messages

## groups table
|Column|Type|Options|
|------|----|-------|
| name  | string | null: false |
| user_id | integer | null: false, foreign_key: true|

### Association
- has_many :users

## messages table
|Column|Type|Options|
|------|----|-------|
| body | text | null: false |
| image | string | null: false |
| user_id | integer | null:false, foreign_key: true |
| group_id | integer | null: false, foreign_key: true |

### Association
- belongs_to :group
- belongs_to :user
