# README

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|-------|
|image|text|-------|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group



## users テーブル
|Column|Type|Options|
|------|----|-------|
|name|integer|null: false|
|email|text|null: false|

### Association
 - has_many :member
 - has_many :messages
 - has_many :groups, through: :group_users
 - has_many :group_users


## groups テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
 - has_many :members
 - has_many :users, through: :group_users
 - has_many :group_users
 - has_many :messages
 
 ## group_users テーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false|
|user_id|integer|null: false, foreign_key: true|

- belongs_to :user
- belongs_to :group



This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
