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
|name|string|null: false|
|mail|string|null: false|
|password|string|null: false|

### Association
- has_many :groups
- has_many :messages
- has_many :groups_users
### index
- add_index :users,  :name



## groupテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :users
- has_many :messages
- has_many :groups_users



## messageテーブル

|Column|Type|Options|
|------|----|-------|
|body|string||
|image|string||
|group_id|string|null: false, foreign_key: true|
|user_id|string|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
