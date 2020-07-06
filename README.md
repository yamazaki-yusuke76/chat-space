# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, add_index: true|
|email|string|null: false,|
|password|string|null: false|

### Association
- has_many :group_users
- has_many :group, through: group_users
- has_many :message

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|null: false, foreign_key|
|user_id|integer|null: false, foreign_key|

### Association
- belongs_to :user
- belongs_to :group

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false,|

### Association
- has_many :group_users
- has_many :users, through: group_users
- has_many :message

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



