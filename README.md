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


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|name|string|null: false|
|password|integer|null: false|


### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :comments


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
|name|string|null: false|


### Association
- has_many :groups_users
- has_many :users, through: :groups_users
- has_many :comments


## commentテーブル

|Column|Type|Options|
|------|----|-------|
|group|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|
|comment|text||
|image|string||


### Association
- belongs_to :user
- belongs_to :group
