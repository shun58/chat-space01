# README

## USERSテーブル（アカウント登録）
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :messages
- has_many :groups, through :user_groups
- has_many :user_groups

## MESSAGESテーブル（チャットメッセージ）
|Column|Type|Options|
|------|----|-------|
|image|string|
|text|text|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## GROUPSテーブル（チャットグループ）
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :messages
- has_many :users, through :user_groups
- has_many :user_groups

## USER_GROUPSテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign key: true|
|group_id|integer|null: false, foreign key: true|
### Association
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

