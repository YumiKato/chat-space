# README

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## tweetsテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|text|-------|
|user_id|integer|null: false, foreign_key: true|

### Association
belongs_to :user
belongs_to :group



## users テーブル
|Column|Type|Options|
|------|----|-------|
|name|integer|null: false|
|email|text|null: false|

### Association
 - has_many :member
 - has_many :tweets
 - has_many :groups, through: :group_users
 - has_many :group_users


## group テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|user_id|integer|null: false, foreign_key: true|

### Association
has_many :members
 - has_many :users, through: :group_users
 - has_many :group_users



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
