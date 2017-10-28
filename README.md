## DB設計

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :users, through: :group-user
- has_many :messages
- has_many :group-users

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|integer|null: false|
|password|integer|null: false|

### Association
- has_many :groups, through: :group_user
- has_many :group-users
- has_many :messages

## group-userテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|reference|null: false, foreign_key: true|
|user_id|reference|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|text|null: false|
|group_id|integer|null: false|
|user_id|integer|null: false|
|created_at|datetime|null: false|
|updated_at|datetime|null: false|

### Association
- belongs_to :group
- belongs_to :user
