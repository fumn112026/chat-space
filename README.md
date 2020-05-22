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
## user table
|Column|Type|Option|
|------|----|------|
|name|string|null: false|
|email|string|unique: true|
|password|text|null :false|

### Association
- has_many :posts
- has_many :groups, through: members
- has_many :members

## post table
|Column|Type|Option|
|------|----|------|
|text|text|
|image|text|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## group table
|Column|Type|Option|
|------|----|------|
|name|string|null: false|

### Association
- has_many :posts
- has_many :members
- has_many :users, through: members

## members table
|Column|Type|Option|
|------|----|------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
