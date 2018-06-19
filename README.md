# README

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|-------|
|image|text|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## users テーブル
|Column|Type|Options|
|------|----|-------|
|name||null: false|
|email|text|null: false|

### Association
 - has_many :messages
 - has_many :groups, through: :group_users
 - has_many :group_users


## groups テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
 - has_many :users, through: :group_users
 - has_many :group_users
 - has_many :messages
 
 
 ## group_users テーブル
|Column|Type|Options|
|------|----|-------|
|group_id|references|null: false|
|user_id|references|null: false, foreign_key: true|

- belongs_to :user
- belongs_to :group



