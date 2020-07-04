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

## users
|Column|Type|Option|
|------|----|------|
|mail|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many : tweets
- has_many : groups, through: users_groups


## tweets
|Column|Type|Option|
|------|----|------|
|text|string||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to: user
- belongs_to: group

## groups
|Column|Type|Option|
|------|----|------|
|name|string|null: false|
### Association
- has_many: tweets
- has_many: users, through: users_groups

## users_groups
|Column|Type|Option|
|------|----|------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
#### Association
- belongs_to: user
- belongs_to: group
