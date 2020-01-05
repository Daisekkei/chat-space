# README

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

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|email|string|null: false|
|user_name|integer|null: false|
|password|integer|null: false|

### Association
- has_many :group, through: :groups_users
- has_many :comment


## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## groupテーブル

|Column|Type|Options|
|------|----|-------|
|group|references|null: false, foreign_key: true|
|group_name|integer|null: false, foreign_key: true|
|member|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- has_many :comment


## commentテーブル

|Column|Type|Options|
|------|----|-------|
|group|references|null: false, foreign_key: true|
|comment|text|null: false, foreign_key: true|
|image|string|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group