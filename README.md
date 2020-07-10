# README

## USERテーブル（アカウント登録）
|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :message
- has_many :group, through :user_group

## MESSAGEテーブル（チャットメッセージ）
|Column|Type|Options|
|------|----|-------|
|image|string|null: true|
|text|text|null: false|
### Association
- belongs_to :user
- has_many :group

## GROUPテーブル（チャットグループ）
|Column|Type|Options|
|------|----|-------|
|groupname|text|null: false, foreign key: true|
|groupmember|integer|null: false, foreign key: true|
### Association
- belongs_to :message
- has_many :user, through :user_group

## USER_GROUPテーブル
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

