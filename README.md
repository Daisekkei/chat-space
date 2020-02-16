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


<<<<<<< Updated upstream
=======

>>>>>>> Stashed changes
## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

<<<<<<< Updated upstream

=======
>>>>>>> Stashed changes
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|name|string|null: false|
|password|integer|null: false|

<<<<<<< Updated upstream

=======
>>>>>>> Stashed changes
### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :comments


## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

<<<<<<< Updated upstream

=======
>>>>>>> Stashed changes
### Association
- belongs_to :group
- belongs_to :user



## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

<<<<<<< Updated upstream

=======
>>>>>>> Stashed changes
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

<<<<<<< Updated upstream

### Association
- belongs_to :user
- belongs_to :group
=======
### Association
- belongs_to :user
- belongs_to :group
>>>>>>> Stashed changes
