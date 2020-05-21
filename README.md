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
## userテーブル
|Column|Type|Option|
|------|----|------|
|name|string|null: false|
|email|string|unique: true|
|password|text|null :false|

### Association
- has_many :posts
- has_many :groups_users

## postテーブル
|Column|Type|Option|
|------|----|------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groupテーブル
|Column|Type|Option|
|------|----|------|
|name|string|null: false|

### Association
- has_many :posts
- has_many :groups_users

## groups_usersテーブル

|Column|Type|Option|
|------|----|------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
